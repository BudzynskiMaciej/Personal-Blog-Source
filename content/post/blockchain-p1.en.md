---
author: "Maciej Budzyński"
title: "What is Blockchain?"
date: "2019-09-30T18:00:00+02:00"
categories: ["programming"]
ENtags: ["programming", "blockchain"]

---

Blockchain is a popular word in the depths of the internet lately. In this article, I will try to demystify what the famous Blockchain is and what it can be useful for.

<!--more-->

# Data Structures

First, it is necessary to explain what data structures are in order to understand what blockchain is. Data structures, in general, are ways of organizing, managing, and storing data in computer memory. More precisely, a data structure is a collection of data values, the relationships between them, and the functions or operations that can be applied to the data. Different data structures serve different purposes, such as relational databases that use B-tree indexes to retrieve data, and some compiler implementations use hash tables to look up identifiers. Data structures include:

* Record, also known as a structure or tuple (e.g., a point with coordinates X, Y)
* Array
* List (singly or doubly linked)
* Object
* Tree
* Hash table
* Graph

and many, many more variations of the above data structures.

# Blockchain

Blockchain is a data structure. Specifically, it is a type of singly linked list containing blocks that are strongly linked together using cryptography. Each block contains the hash of the previous block, a timestamp, and transaction data. The exception is the so-called Genesis Block. This is the first block that forms the chain of links with other blocks. The premise of the blockchain is resistance to data modification and easy verification that the data has not been tampered with. Modifying any block results in generating completely different hashes for subsequent blocks, which allows for easy verification that the data has not been tampered with.

# Why and for whom?

Currently, the application of blockchain is primarily to handle various transactions such as:

* Stocks
* Currencies
* Trade

The main application of this data structure can be seen in cryptocurrencies like Bitcoin. In the next articles, I will try to implement an example blockchain.