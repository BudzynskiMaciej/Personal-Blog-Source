---
author: "Maciej Budzyński"
title: "Which programming language to choose as a beginner, or multi-Hello World"
date: "2018-04-28T15:04:50+02:00"
categories: ["guide", "programming"]
ENtags: ["golang", "javascript", "java", "c#", "c++", "c", "python", "ruby", "php", "haskell", "programming"]
#cover:
#  image: images/msg.png
#  caption: "Generated using [OG Image Playground by Vercel](https://og-playground.vercel.app/)"
#ShowToc: true
#TocOpen: false
---

Are you wondering which programming language to choose? Have no idea which one to pick?
Then this post is for you. I have prepared short descriptions of various programming
languages and the basic Hello World program code.

<!--more-->
Golang
------
{{< highlight golang >}}
package main
import "fmt"
func main(){
    fmt.Printf("Hello World\n")
}
{{< /highlight >}}

Statically typed, multi-paradigm programming language developed by Google employees
Robert Griesemer, Rob Pike, and Ken Thompson in 2009. It has a built-in Garbage Collector.
Significantly simplifies concurrent programming thanks to so-called GoRoutines. Functions
can return more than one result. Unfortunately, as of now, Go 1.10 does not support
generic types.

JavaScript
----------
{{< highlight js >}}
console.log("Hello World");
{{< /highlight >}}

Frontend language. Required when writing web applications. Used to create interactive
views on web pages. Dynamically typed (duck typing), multi-paradigm, prototype-based
programming language developed by Netscape in 1995. Thanks to its server-side
implementation NodeJS, it has a huge library of frameworks including Angular from Google
and React from Facebook.

Java
----
{{< highlight java >}}
class Hello{
    public static void main(){
        System.out.println("Hello World");
    }
}
{{< /highlight >}}

Fully object-oriented, statically typed language. Currently one of the most popular
programming languages in which you can find a job without much trouble. Created in 1995
by Sun Microsystems. Its main application is enterprise-class web applications. Often
used with the Spring Framework to create applications. Java was designed with
architecture independence in mind, allowing it to run on any machine with a Java Virtual
Machine.

C#
--
{{< highlight csharp >}}
class HelloWorld
{
    static void Main()
    {
        System.Console.WriteLine("Hello, World!");
    }
}
{{< /highlight >}}

Microsoft's answer to Java. Also created as a fully object-oriented, statically typed
programming language. It has many elements of C++ and Java. The .NET virtual machine
allows it to run on many systems, mainly thanks to .NET Core.

C
-
{{< highlight c >}}
#include <stdio.h>

main()
{
    printf("Hello World!\n");
}
{{< /highlight >}}

One of the oldest languages, currently used in writing microcontrollers. It is also used
in the development of the Linux kernel. It does not have classes, but it is small in size
and can be compiled on any platform. It is a statically typed language.

C++
---
{{< highlight cpp >}}
#include <iostream.h>

int main()
{
    cout << "Hello World!";
    return 0;
}
{{< /highlight >}}

Enhanced C, has classes, templates (generic types), inheritance mechanisms. Overall, it
is C on steroids. Used where the speed of our applications matters.

Python
------
{{< highlight python3 >}}
print("Hello World")
{{< /highlight >}}

Dynamically typed, interpreted language. Very easy to learn, it finds use in many fields
of computer science, from simple scripts, through websites (using Django or Flask
frameworks), to Artificial Intelligence (Machine Learning, Deep Learning). Thanks to
dynamic typing, we do not have to worry about specifying data types, but since it is an
interpreted language, we cannot detect errors before running the application, and the
performance of our applications will not be as good as in the case of applications
written in C or C++ (although it all depends on the algorithm used).

Ruby
----
{{< highlight ruby >}}
puts 'Hello, world!'
{{< /highlight >}}

Like Python, it is a dynamically typed and interpreted language. Currently, its main
application is WebDev thanks to the Ruby on Rails framework, which allows for quick
prototyping and writing web applications. Ruby on Rails itself has a scaffolding
mechanism, allowing us to create a simple site with databases, views, and controllers in
a few minutes.

PHP
---
{{< highlight php >}}
<?php echo '<p>Hello World</p>'; ?> 
{{< /highlight >}}

A language considered by many to be dying, intended exclusively for WebDev. Nevertheless,
it is still very popular thanks to the CMS called WordPress, which was written in PHP.
WordPress itself does not require knowledge of PHP, but writing plugins may require
knowledge of PHP.

Haskell
-------
{{< highlight haskell >}}
main = putStrLn "Hello World"
{{< /highlight >}}

A language with a functional programming paradigm. Ideal for learning this style of
programming. I have not had the opportunity to use it, so I will not write much about it.

Malbolge
--------
{{< highlight malbolge >}}
(=<`$9]7<5YXz7wT.3,+O/o'K%$H"'~D|#z@b=`{^Lx8%$Xmrkpohm-kNi;gsedcba`_^]\[ZYXWVUTSRQPONMLKJIHGFEDCBA@?>=<;:9876543s+O<oLm
{{< /highlight >}}