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

`_1` is a method name. Specifically tuples have a method named `_1`, which returns the first element of the tuple. So `_._1 < _._1` means "call the `_1` method on both arguments and check whether the first is less than the second".

`_++_` concatenates both arguments (assuming the first argument has a `++` method that performs concatenation).
