---
author: "Maciej Budzyński"
title: "Jaki język programowania wybrać na początek, czyli multi-Hello World"
date: "2018-04-28T15:04:50+02:00"
categories: ["poradnik", "programming"]
tags: ["golang", "javascript", "java", "c#", "c++", "c", "python", "ruby", "php", "haskel", "programming"]
#cover:
#  image: images/msg.png
#  caption: "Generated using [OG Image Playground by Vercel](https://og-playground.vercel.app/)"
#ShowToc: true
#TocOpen: false
---

Zastanawiasz sie nad wyborem języka programowania? Nie masz pojęcia który z nich wybrać?
W takim razie ten post jest dla Ciebie. Przygotowałem w nim krótkie opisy różnych języków
programowania oraz podstawowy kod programu Hello World.

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

Statycznie typowany, wieloparadygmatowy język programowania opracowany przez pracowników
Google Roberta Griesemera, Roba Pike'a oraz Kena Thompsona w 2009 roku. Posiada wbudowany
Kolektor Śmieci (ang. Garbage Collector). Znacząco ułatwia programowanie współbierzne,
dzięki tak zwanym GoRutines. Funkcje mogą zwracać więcej niż jeden wynik. Niestety na
chwilę obecną Go 1.10 nie wspiera typów generycznych.

JavaScript
----------
{{< highlight js >}}
console.log("Hello World");
{{< /highlight >}}

Język frontendu. Wymagany podczas pisania aplikacji internetowych. Służy do tworzenia
interaktywnych widoków na stronach WWW. Typowany dynamicznie (kacze typowanie),
wieloparadygmatowy, oparty na prototypach język programowania opracowany przez firmę
Netscape w 1995 roku. Dzięki swojej serwerowej implementacji NodeJS posiada ogromną
bibliotekę frameworków między innymi Angular od Google oraz React od Facebooka. 

Java
----
{{< highlight java >}}
class Hello{
	public static void main(){
		System.out.println("Hello World");
	}
}
{{< /highlight >}}

Język w pełni obiektowy, typowany statycznie. Obecnie jest to jeden z najpopularniejszych
języków programowania w którym można znaleźć pracę bez większych problemów. Stworzony
w 1995 przez Sun Microsystems. Jego główne zastosowanie to aplikacje webowe klasy
enterprise. Często wykorzystuje się przy nim Spring Framework do tworzenia aplikacji.
Java powstała  z myślą niezależności od architektury, dzięki czemu możemy uruchomić
ją na każdej maszynie posiadającą wirtualną maszynę Javy.

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

Odpowiedź Microsoftu na Javę. Również stworzony jako w pełni obiektowy, statycznie
typowany język programowamnia. Posiada wiele elementów języka C++ oraz Javy.
Wirtualna maszyna .NET pozwala na uruchomienie na wielu systemach, głównie za sprawą
.NET Core

C
-
{{< highlight c >}}
#include <stdio.h>

main()
{
    printf("Hello World!\n");
}
{{< /highlight >}}

Jeden z najstarszych języków, obecnie wykorzystywany przy pisaniu mikrokontrolerów.
Obecnie też stosuje się go przy rozwoju jądra Linux. Nie posiada klas, jednak jest
niewielkich rozmiarów i potrafi się kompilować na każdej platformie. Jest to język
statycznie typowany.

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

Ulepszone C, posiada klasy, szablony(typy generyczne), mechanizmy dziedziczenia.
Ogółem rzecz biorąc jest to C na sterydach. Wykorzystywany tam, gdzie liczy się,
szybkość naszych aplikacji.

Python
------
{{< highlight python3 >}}
print("Hello World")
{{< /highlight >}}

Język dynamicznie typowany, interpretowany. Bardzo prosty do nauczenia, znajduje
wykorzystanie w wielu dziedzinach informatyki, od prostych skyptów, poprzez strony
internetowe (z wykorzystaniem frameworków Django lub Flask), aż do Sztucznej
Inteligencji (Machine Learning, Deep Learning). Dzięki dynamicznemu typowaniu
możemy nie przejmować się precyzowaniem typu danych, niestety ponieważ jest to
język interpretowany nie zdołamy wykryć błedów przed uruchomieniem aplikacji, oraz
wydajność naszych aplikacji nie będzie tak dobra jak w przypadku apliacji
pisanych w C bądź C++ (chodź wszystko zależy od zastosowanego algorytmu).

Ruby
----
{{< highlight ruby >}}
puts 'Hello, world!'
{{< /highlight >}}

Podobnie jak Python jest to język dynamicznie typowany oraz interpretowany.
Obecnie jego główne zastosowanie to WebDev dzięki frameworkowi Ruby on Rails,
który pozwala na szybkie prototypowanie i pisanie aplikacji internetowych.
Sam Ruby on Rails posiada mechanizm rusztowania naszych aplikacji (Scaffolding),
dzięki czemu prostą stronę z wykorzystaniem baz danych, widoków oraz kontrolerów
stworzymy w kilka minut.

PHP
---
{{< highlight php >}}
<?php echo '<p>Hello World</p>'; ?> 
{{< /highlight >}}

Język przez wielu uważany za wymierający, przeznaczony wyłącznie do WebDev.
Mimo wszystko wciąż jest bardzo popularny dzięki CMSowi zwanemu Wordpress, który
został napisany właśnie w PHP. Sam Wordpress nie wymaga znajomości PHP, jednak
pisanie dodatków może już wymagać od nas znajomości PHP.

Haskell
-------
{{< highlight haskell >}}
main = putStrLn "Hello World"
{{< /highlight >}}

Język z paradygmatem programowania funkcyjnego. Idealny do nauki własnie takiego
stylu programowania. Nie było mi dane z niego korzystać, więc wiele na jego temat
nie napiszę.

Malbolge
--------
{{< highlight malbolge >}}
(=<`$9]7<5YXz7wT.3,+O/o'K%$H"'~D|#z@b=`{^Lx8%$Xmrkpohm-kNi;gsedcba`_^]\[ZYXWVUTSRQPONMLKJIHGFEDCBA@?>=<;:9876543s+O<oLm
{{< /highlight >}}