---
author: "Maciej Budzyński"
title: "Jak uzyskać dostęp do admina na Linuxie wykorzystując Dockera?"
date: "2021-07-24T20:00:00+02:00"
categories: ["programming"]
tags: ["programming", "docker", "linux"]

---

Nie posiadasz uprawnień administratora na lokalnym sprzęcie? Posiadasz Linuxa oraz Dockera? 
Jeżeli odpowiedź na powyższe pytania brzmi tak to w tym artykule pokażę Ci jak wykorzystać 
Dockera do modyfikacji pliku sudoers, dzięki czemu uzyskasz uprawnienia administratora.

<!--more-->

# Wymagania wstępne

Przedstawiony tutaj sposób wymaga, aby użytkownik z ograniczeniami miał dostęp do komend dockerowych, 
tzn. użytkownik należy do grupy docker. Konfiguracja dockera wymaga, aby użytkownik należał do 
tej grupy. Sposób ten działa wyłącznie na systemie Linux (testowane na Ubuntu).

# TLDR

* Odpalenie alpine linuxa z zamontowaniem pliku `/etc/sudoers` jako `sudoers` w kontenerze:
{{< highlight bash >}}
docker run -it -v /etc/sudoers:/sudoers --rm alpine /bin/sh
{{< /highlight >}}

* Zmiana uprawnień w celu edycji pliku `sudoers` za pomocą vi:
{{< highlight bash >}}
chmod 777 sudoers
vi sudoers
{{< /highlight >}}

* Dodanie użytkownikowi wymaganych uprawnień w pliku `sudoers` (klawisz `i` w celu dodania wpisu): 
{{< highlight bash >}}
# Pomiedzy user a ALL wymagana jest tabulacja (raz TAB, nie 4 spacje)
user	ALL=(ALL:ALL) ALL
{{< /highlight >}}

* Wyjście z zapisem z vi:
{{< highlight bash >}}
:wq
{{< /highlight >}}

* Ponowna zmiana uprawnień pliku `sudoers` na domyślne wartości oraz wyjście z konsoli kontenera:
{{< highlight bash >}}
chmod 755 sudoers
exit
{{< /highlight >}}

* Weryfikacja zmian w pliku `sudoers`:
{{< highlight bash >}}
cat /etc/sudoers
sudo su
{{< /highlight >}}

# Opis poszczególnych komend

## docker run -it -v /etc/sudoers:/sudoers --rm alpine /bin/sh

Komenda ta pozwala na pobranie obrazu alpine linuxa, a następnie odpalenie kontenera z tego obrazu. 
Parametr `-it` odpowiada za odpalenie trybu interaktywnego (pozostawia otwarty STDIN, nawet jeśli nie 
jest podłączony) oraz przydzielenie pseudo-TTY. 
Parametr `-v` wiążę katalog bądź plik hosta z wolumenem kontenera. W tym przypadku tworzymy powiązanie 
dla pliku hosta `/etc/sudoers` z plikiem `sudoers` w katalogu głównym naszego kontenera. 
Parametr `--rm` sprawia, że po zamknięciu i wyjściu z shella, utworzony kontener zostanie usunięty. 
Fragment `alpine /bin/sh` odpowiada za wybranie obrazu, z którego zostanie utworzony kontener (w tym 
przypadku linux alpine) oraz odpalenie polecenia (programu) `/bin/sh`, czyli powłoki systemu (shell).

## chmod 777 sudoers oraz vi sudoers

Plik `/etc/sudoers` domyślnie jest zabezpieczony przed edycją. Ze względu, że alpine jest minimalistyczną 
dystrybucją linuxa posiada domyślnie edytor plików vi. Pliki `sudoers` powinny być edytowane za pomocą 
visudo, jednak w alpine nie ma domyślnie tego zainstalowane. W celu edycji pliku należy nadać pełne 
uprawnienia do pliku obecnemu użytkowniki za pomocą komendy `chmod 777 sudoers` odpalonej w kontenerze z 
alpine. Następnie można otworzyć plik sudoers wykorzystując edytor vi za pomocą komendy: `vi sudoers`. 
Aby móc wpisywać tekst w edytorze vi należy nacisnąć na klawiaturze przyciski `i`.

## user	ALL=(ALL:ALL) ALL

Powyższy wpis pozwala na dodanie użytkownikowi `user` uprawnień do wykonywania wszystkich komend. 
Pierwsze pole wskazuje nazwę użytkownika, którego dotyczy reguła (user). 
Pierwsze „ALL” oznacza, że ta reguła dotyczy wszystkich hostów. 
Drugie „ALL” oznacza, że użytkownik user może uruchamiać polecenia jako wszyscy użytkownicy. 
Trzecie „ALL” oznacza, że użytkownik user może uruchamiać polecenia jako wszystkie grupy. 
Czwarte „ALL” oznacza, że te zasady dotyczą wszystkich poleceń (komend). 
Należy pamiętać o zachowaniu odpowiedniego formatowania w pliku. W przypadku Ubuntu między user, a ALL 
był odstęp z wykorzystaniem pojedynczej tabulacji (nie cztery spacje). Osobiście nie jestem, pewien 
czy użycie pojedynczej spacji, bądź 4 spacji nie zepsuje niczego, więc dla pewności zachowałem docelowe 
formatowanie.

## Wyjście z vi 

W celu wyjścia z edytora vi zapisując zmiany, należy nacisnąć na klawiaturze klawisz `esc`, a następnie wpisać 
`:wq`. Polecenia po dwukropku to komendy dla vi. `w` oznacza, iż chcemy zapisać zmiany wprowadzone w pliku 
natomiast `q` oznacza zamknięcie pliku.

## chmod 755 sudoers oraz exit

Zmieniamy uprawnienia do pliku sudoers na domyślne wartości przed edycją, a następnie wychodzimy z powłoki 
kontenera za pomocą komendy `exit`. Po wyjściu kontener z alpine zostanie usunięty. Pozostanie wyłącznie 
pobrany obraz na dysku. 

## cat /etc/sudoers oraz sudo su

W celu weryfikacji dostępów możemy wykorzystać polecenie `cat /etc/sudoers`, aby sprawdzić, czy wpisy 
poprawnie się dodały. Możemy też użyć komendy `sudo su`, aby sprawdzić, czy możemy wykonywać polecenia 
jako sudo.

# Wniosek

Jak widać docker pozwala na zmianę uprawnień dla użytkownika i modyfikację plików, do których domyślnie 
nie posiadamy dostępu. Grupa Docker należy do grup administratorskich, przez co użytkownik będący w tej 
grupie posiadający dostęp do wykonywania komend dockera, ma możliwość dowolnej modyfikacji plików, bez 
konieczności dostępu do praw administratora. 
