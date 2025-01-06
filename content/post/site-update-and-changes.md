---
author: "Maciej Budzyński"
title: "Odświeżenie i aktualizacja strony"
date: "2025-01-06T13:00:00+02:00"
categories: ["programming"]
tags: ["programming", "go", "hugo"]

---

Bardzo dawno tutaj nie pisałem, a moja aktywność opierała się o coroczne podbijanie 
znaku copyright. Z powodu aktualizacji Hugo, byłem zmuszony do odświeżenia strony i 
aktualizacji znajdujących się tu treści.

<!--more-->

## Zmiana template

Aby zmienić template, wykonałem następujące kroki:

1. Usunąłem stary template z moimi modyfikacjami `hugo-dusk`.
2. Dodałem nowy template `PaperMod` do katalogu `themes`.
3. Zmigrowałem plik `config.toml` na `hugo.yaml`.

## Konfiguracja

Po zmianie template, musiałem dostosować konfigurację strony. Wprowadziłem następujące zmiany w pliku `hugo.yaml`:

- Zaktualizowałem sekcję `params` o nowe ustawienia dostępne w template `PaperMod`.
- Dodałem nowe sekcje konfiguracyjne, które umożliwiają lepsze zarządzanie treścią i wyglądem strony.

## Artykuły w języku angielskim

Kolejną nowością na stronie są artykuły w języku angielskim. Aby dodać wsparcie dla wielu języków, wprowadziłem następujące zmiany:

1. Dodałem sekcję `languages` w pliku `hugo.yaml`:

```yaml
languages:
  pl:
    languageName: "Polski"
    weight: 1
  en:
    languageName: "English"
    weight: 2
```

2. Wszyskie artykuły zostały zduplikowane i zmieniono ich nazwy z `*.md` na `*.en.md`
3. Artykuły te przetłumaczyłem z wykorzystaniem narzędzi AI.

Dzięki tym zmianom, strona jest teraz dostępna zarówno dla polskojęzycznych, jak i anglojęzycznych użytkowników.

Mam nadzieję, że te zmiany przypadną Wam do gustu i ułatwią korzystanie ze strony, a ze swojej strony 
liczę na to, że uda się tu zamieścić więcej pulikacji.