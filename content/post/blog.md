+++
categories = ["poradnik", "opinia"]
date = "2018-04-28T16:40:20+02:00"
tags = ["golang", "hugo", "wordpress", "blog", "story"]
title = "Blog oparty o generator stron statycznych Hugo"

+++

W aktualnych czasach każdy posiada swoją stronę w internecie. Ja postanowiłem założyć bloga 
opartego o technologię Hugo.

<!--more-->
Początki blogowania
-------------------
Swoją przygodę rozpocząłem z blogiem stworzonym za pomocą **Wordpress**a. Możliwość konfiguracji, 
ilość szablonów, dodatków to wszystko przytłaczało. Wordpress był bardzo prostm narzędziem,
jednak miał też kilka wad, wymagał PHP oraz Bazy Danych, a wraz z rozrostem strony zwiększał się
jej czas ładowania. W dodatku darmowy hosting nie mógł utrzymać dużego ruchu na stronach.

Generatory stron statycznych
----------------------------
Wtedy zaznajomiłem się z narzędziami do generowania stron statycznych. Rozpocząłem od wykorzystania
najpopularniejszego z nich **Jekyll**a. I tu pojawiły się pierwsze problemy. Jako użytkownik Windowsa
zacząłem mieć problemy z konfiguracją i instalacją **Ruby**. Problemy z certyfikatami, problemy z
bundlerem, z aktualizacją dodatków jak i samego **Jekyll**a. Mimo, iż **Jekyll** to potężne narzędzie
pozwalające instalować dodatki i dowolnie modyfikować wygląd strony, jednak Ruby + Windows = Męczarnia.

Hugo, generator stron statycznych oparty o GoLang
-------------------------------------------------
Postanowiłem poszukać alternatywy do **Jekyll**a i w ten sposób natrafiłem na Hugo, a właściwie goHugo
(wpisanie samej frazy Hugo może wiązać się ze znalezieniem znanego z interaktywnego programu telewizyjnego
dla dzieci trolem imieniem Hugo)![Hugo](https://lh3.googleusercontent.com/TfWnTBtz0eNVqKmeIchhQ4KJ1MBsFfyHr79oSZNVs79LNzaWPZkPY2TAU8y3vkUw7F0Y=w300)
**Hugo** jest podobnie jak **Jekyl** generatorem stron statycznych, jednak napisanym w kompilowanym języku 
**GoLang**. Nie musimy znać się absolutnie na **Go** by móc korzystać z **Hugo**. Jedyna wiedza jakiej 
potrzebujemy to ta związana z **HTML** i **CSS** jeśli chcemy edytować, bądź tworzyć własne szablony oraz
**Markdown** do pisania naszych postów.

| Zalety        | Wady          |
|:-------------:|:-------------:|
| col 3 is      | right-aligned |
| col 2 is      | centered      |
| zebra stripes | are neat      |

Rozpoczęcie przygody z Hugo
---------------------------
Aby rozpocząć przygodę z Hugo należy [pobrać jego najnowszą wersję z repozytorium na GitHub](https://github.com/gohugoio/hugo/releases "Hugo Download Page").
Stamtąd pobieramy najnowszą wersję w zależności od posiadanego systemu operacyjnego:
*W moim przypadku na dzień pisania newsa jest to wersja hugo_0.24.1_Windows-64bit.zip*
Na Windows wystarczy wypakować plik hugo.exe w dowolnym miejscu: *Polecam C:/Hugo/*
Po czym musimy dodać katalog zawierający wyżej wymieniony plik do zmiennej środowiskowej **PATH**. Jeśli
wszystko zrobiliśmy poprawnie powinna zadziałać komenda *hugo help*. w przypadku problemów odsyłam was do
[oficjalnej dokumentacji Hugo związaną z jego instalacją na systemie Windows w języku angielskim](https://gohugo.io/tutorials/installing-on-windows/ "Hugo - Installing on Windows").
#### Na koniec zostawiam film związany z szybką instalacją i aktywacją naszego pierwszego bloga w Hugo
{{< youtube w7Ft2ymGmfc >}}