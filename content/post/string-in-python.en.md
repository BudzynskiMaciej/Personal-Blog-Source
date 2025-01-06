---
author: "Maciej Budzyński"
title: "Beautifying Strings: How to Format Strings in Python"
date: "2018-09-17T20:00:00+02:00"
categories: ["programming"]
ENtags: ["python", "programming"]

---
In Python, there were two methods of formatting strings. This situation lasted until the release of
Python 3.6, with the advent of f-strings. Today, I will try to discuss all formatting methods and provide examples of their use.

<!--more-->

# Code we will work with

We will use a few simple variables, which I will try to display using each of the available formatting methods.

{{< highlight python3 >}}
first_name = "John"
last_name = "Doe"
born_year = 1978
current_age = 40
dict = {'text':'One', 'value': 1}
{{< /highlight >}}

# Old formatting using the '%' sign

This formatting has been in Python for a long time. Currently, this method is not recommended by
Python documentation, as it has some shortcomings and can cause problems with displaying tuples and lists. Below is an example of using this formatting:

{{< highlight python3 >}}
print("Hello %s %s. Your born year is %d. You are %d years old", first_name, last_name, born_year, current_age)
{{< /highlight >}}

What does %s mean? It simply informs the interpreter that we want to read a string. Available modifiers:

* **%s** - String (or any object that has a **repr** method, e.g., an array)
* **%d** - Integers
* **%f** - Floating-point numbers
* **%.(X)** - Floating-point number with precision up to X decimal places
* **%X** - Integer represented in hexadecimal (base-16) notation

# Formatting using str.format()

This option was introduced in Python 2.6. It is improved formatting compared to %-formatting.
With _str.format()_, the fields we want to substitute are represented by `{}`. Example:

{{< highlight python3 >}}
print("Hello {2} {3}. Your born year is {1}. You are {0} years old.".format(current_age, born_year, first_name, last_name))
{{< /highlight >}}

We can also display the contents of dictionaries by unpacking them:

{{< highlight python3 >}}
print("{text} is {value}.".format(**dict))
{{< /highlight >}}

# The new way, f-Strings in Python 3.6

The introduction of f-Strings made formatting even simpler. Example:

{{< highlight python3 >}}
print(f"Hello {first_name} {last_name}. Your born year is {born_year}. You are {current_year} years old")
{{< /highlight >}}

That's all, f-Strings are executed at runtime. Just put a previously defined variable in `{}`. You can also use expressions, e.g.:

{{< highlight python3 >}}
print(f"{2 * 6}")
{{< /highlight >}}

This code will display the value of the expression `2 * 6`, which is `12`. You can also call functions:

{{< highlight python3 >}}
name = "jane"
print(f"{name.capitalize()}")
{{< /highlight >}}

The above code will display the string: `Jane`. We can also display the contents of dictionaries:

{{< highlight python3 >}}
print(f"{dict['text']} is {dict['value']}.")
{{< /highlight >}}

As you can see, it is worth using f-Strings as they increase our productivity and do not obscure the code.
They are also slightly faster to execute than %-Strings and str.format().