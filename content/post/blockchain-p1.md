---
author: "Maciej Budzyński"
title: "Czym jest Blockchain?"
date: "2019-09-30T18:00:00+02:00"
categories: ["programming"]
tags: ["programming", "blockchain"]

---

Blockchain (po polsku łańcuch bloków) jest ostatnio popularnym słowem w odmętach internetu. 
W tym artykule postaram się zdemaskować czym jest sławny Blockchain oraz do czego może
być przydatny.

<!--more-->

# Struktury danych

Na początku należy wytłumaczyć, czym są struktury danych, aby móc zrozumieć czym jest 
blockchain. Struktury danych (ang. data structures) w ogólnym skrócie są sposobem organizacji, 
zarządzania oraz przechowywania danych w pamięci komputera. Dokładniej, struktura danych to 
zbiór wartości danych, relacje między nimi oraz funkcje, bądź operacje, które można zastosować 
dla danych. Różne struktury danych służą do różnych celów jak na przykład relacyjne bazy danych, 
które wykorzystują indeksy drzewa-B do pobierania danych oraz pewne implementacje 
kompilatorów używają tabel mieszających (ang. Hash Table) do wyszukiwania identyfikatorów. 
Do struktur danych zaliczamy:

* Rekord, zwaną też strukturą, bądź krotką (np. punkt o współrzędnych X, Y)
* Tablicę
* Lista (jedno bądź dwukierunkowa)
* Objekt
* Drzewo
* Tablica mieszająca
* Graf

oraz wiele, wiele więcej różnych wariancji powyższych struktur danych.

# Blockchain

Blockchain to struktura danych. Konkretnie jest to rodzaj jednokierunkowej listy zawierających 
silnie powiązane ze sobą bloki za pomocą kryptografii. Każdy blok zawiera hasz poprzedniego 
bloku, znacznik czasu oraz dane transakcji. Wyjątkiem jest tak zwany Genesis Block (pol. blok 
początkowy). Jest to pierwszy blok tworzący łańcuch powiązań z innymi blokami. Założeniem 
łańcucha bloków jest odporność na modyfikację danych oraz łatwa weryfikacja, czy dane nie 
zostały podrobione. Modyfikacja dowolnego bloku, skutkuje wygenerowaniem zupełnie innych 
haszy dla kolejnych bloków, co pozwala na łatwą weryfikację czy dane nie zostały podrobione.

# A po co to i na co to komu?

Obecnie zastosowanie blockchain to przedewszystkim obsługa różnych transakcji jak na przykład:

* Akcje
* Waluty
* Handel

Główne zastosowanie tej struktury danych można zauważyć w kryptowalutach np. Bitcoin.
W następnych artykułach postaram się zaimplementować przykładowy łańcuch bloków.