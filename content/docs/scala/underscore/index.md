---
date:
nav_weight: 2
title: Underscore (_) in Scala
linkTitle: Underscore (_) in Scala
series:
  - Scala
categories:
  - Scala Syntax
tags:
  - underscore
images:
featured: false
authors:
  - Fuad Efendi
---

## What do `_._1` and `_++_` mean in Scala? 

### `_._1` 

`_1` is a method name. Specifically tuples have a method named `_1`, which returns the first element of the tuple. So `_._1 < _._1` means "call the `_1` method on both arguments and check whether the first is less than the second".

#### Example
`.toList.sortWith(_._1 < _._1)` 

`_._1` calls the method `_1` on the wildcard parameter `_`, which gets the first element of a tuple. Thus, `sortWith(_._1 < _._1)` sorts the list of tuple by their first element.

### `_++_` 

`_++_` concatenates both arguments (assuming the first argument has a `++` method that performs concatenation). `_++_` calls the method ++ on the first wildcard parameter with the second parameter as an argument.

#### Example
`++` does concatenation for sequences. `.reduce(_++_)` concatenates a list of sequences together. You can also use `flatten` for that.


