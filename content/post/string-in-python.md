+++
categories = ["programming"]
date = "2018-09-17T20:00:00+02:00"
tags = ["python", "programming"]
title = "Upiększanie ciągów znaków, czyli jak formatować stringi w Pythonie"

+++

W pythonie istniały dwie metody formatowania stringów. Sytuacja ta trwała do czasu pojawienia się 
Python 3.6, wraz z nadejściem f-stringów. Dziś postaram się omówić wszystkie metody formatowania, 
oraz podam przykład ich stosowania.

<!--more-->

# Kod z którym będziemy pracować

Wykorzystamy pare prostych zmiennych, które postaram się wyświetlić za pomocą każdej z dostępnych 
metod formatujących.

```python
first_name = "John"
last_name = "Doe"
born_year = 1978
current_age = 40
dict = {'text':'One', 'value': 1}
```

# Stare formatowanie poprzez znak '%'

Formatowanie to znajduje się w Pythonie od dawien dawna. Obecnie metoda ta nie jest zalecana przez 
dokumentację Pythona, gdyż posiada pewne niedociągłości i może powodować problemy z wyświetlaniem 
krotek oraz list. Poniżej przedstawiam przykład użycia tego formatowania: 

```python
print("Hello %s %s. Your born year is %d. You are %d years old", first_name, last_name, born_year, current_age)
```

Co oznacza %s? To porostu informuje interpreter o tym, że chcemy odczytać string. Dostępne modyfikatory: 
- **%s** - Ciąg znaków (bądź każdy obiekt który posiada metodę __repr__ np. tablica)) 
- **%d** - Liczby całkowite 
- **%f** - Liczby zmiennoprzecinkowe
- **%.(X)** - Liczba zmiennoprzecinkowa z dokładnością do X liczb po przecinku 
- **%X** - Liczba całkowita reprezentowana w zapisie hexadecymalnym (szesnastkowym)

# Formatowanie poprzez str.format()

Ta opcja została wprowadzona w Python 2.6. Jest to ulepszone formatowanie względem %-formatowania. 
Dzięki *str.format()* pola które zamierzamy podstawić reprezentujemy za pomocą znaków `{}`. Przykład: 

```python
print("Hello {2} {3}. Your born year is {1}. You are {0} years old.".format(current_age, born_year, first_name, last_name))
```

Możemy też wyświetlać zawartość słowników poprzez ich rozpakowywanie:

```python
print("{text} is {value}.".format(**dict))
```

# Nowa droga, czyli f-Stringi w Pythonie 3.6

Wprowadzenie f-Stringów uczyniło formatowanie jeszcze prostrzym. Przykład:

```python
print(f"Hello {first_name} {last_name}. Your born year is {born_year}. You are {current_year} years old")
```

To wszystko, f-Stringi są wykonywane w czasie uruchomienia. Poprostu w `{}` podajesz zmienną zdefiniowaną 
wcześniej. Możesz też używać wyrażeń, np.:

```python
print(f"{2 * 6}")
```

Ten kod wyświetli wartość wyrażenia `2 * 6`, czyli `12`. Możesz też wywoływać funkcje: 

```python
name = "jane"
print(f"{name.capitalize()}")
```

Powyższy kod wyświetli napis: `Jane`. Możemy też wyświetlać zawartość słowników: 

```python
print(f"{dict['text']} is {dict['value']}.")
```

Jak widać warto korzystać z f-Stringów, gdyż zwiększają naszą produktywność oraz nie zaciemniają kodu. 
Również są też nieco szybsze w wykonaniu niż %-Stringi oraz str.format().