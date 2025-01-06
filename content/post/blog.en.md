---
author: "Maciej Budzyński"
title: "Blog based on the Hugo static site generator"
date: "2018-04-28T16:40:20+02:00"
categories: ["guide", "opinion"]
ENtags: ["golang", "hugo", "wordpress", "blog", "story"]

---

Nowadays, everyone has their own website on the internet. I decided to start a blog based on Hugo technology.

<!--more-->
Beginnings of blogging
-------------------
I started my adventure with a blog created using **Wordpress**. The configuration possibilities, the number of templates, and add-ons were overwhelming. Wordpress was a very simple tool, but it also had some drawbacks, it required PHP and a Database, and as the site grew, its loading time increased. Additionally, free hosting could not handle high traffic on the sites.

Static site generators
----------------------------
Then I got acquainted with tools for generating static sites. I started by using the most popular one, **Jekyll**. And here the first problems appeared. As a Windows user, I started having problems with the configuration and installation of **Ruby**. Problems with certificates, problems with bundler, with updating add-ons, and **Jekyll** itself. Although **Jekyll** is a powerful tool that allows you to install add-ons and freely modify the appearance of the site, Ruby + Windows = Torture.

Hugo, a static site generator based on GoLang
-------------------------------------------------
I decided to look for an alternative to **Jekyll** and thus I came across Hugo, or rather goHugo (typing just the phrase Hugo may result in finding a well-known troll named Hugo from an interactive children's TV show)![Hugo](https://lh3.googleusercontent.com/TfWnTBtz0eNVqKmeIchhQ4KJ1MBsFfyHr79oSZNVs79LNzaWPZkPY2TAU8y3vkUw7F0Y=w300)
**Hugo** is, like **Jekyll**, a static site generator, but written in the compiled language **GoLang**. We don't need to know **Go** at all to use **Hugo**. The only knowledge we need is related to **HTML** and **CSS** if we want to edit or create our own templates, and **Markdown** to write our posts.

| Advantages        					| Disadvantages      							  	|
|:-----------------------------------------------------:|:---------------------------------------------------------------------:|
| Easy post creation using **Markdown**	| Requires knowledge of **GIT** if we intend to use GitHub Pages 	|
| Easy management of appearance thanks to **HTML** and **CSS**	| Adding special functions may require knowledge of **Go**		|
| Simple and extensive documentation		| On most hostings, it is required to upload the entire Public folder	|

Starting the adventure with Hugo
---------------------------
To start the adventure with Hugo, you need to [download the latest version from the GitHub repository](https://github.com/gohugoio/hugo/releases "Hugo Download Page").
From there, download the latest version depending on your operating system:
*In my case, at the time of writing this news, it is version hugo_0.40.1_Windows-64bit.zip*
On Windows, just extract the hugo.exe file anywhere: *I recommend C:/Hugo/*
Then we need to add the directory containing the aforementioned file to the **PATH** environment variable. If we did everything correctly, the command *hugo help* should work. In case of problems, I refer you to the [official Hugo documentation related to its installation on Windows in English](https://gohugo.io/tutorials/installing-on-windows/ "Hugo - Installing on Windows").
#### Finally, I leave a video related to the quick installation and activation of our first blog in Hugo
{{< youtube w7Ft2ymGmfc >}}