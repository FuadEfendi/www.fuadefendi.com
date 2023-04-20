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


## Scala `_=` vs. classic Java "getters" and "setters"

Functional Programming (FP) discourages data structures that maintain state, so Scala style tries to avoid setters whenever possible.

Getters and setters (if you define mutable property with `var`) are automatically created in Scala and seamlessly used. Java does not have this so you need to create them manually.

Scala already automatically creates getters and setters for fields. This is because fields are never actually public. Instead, all fields are private, and a getter `def <fieldname>: <fieldtype>` is created. A setter `def <fieldname>_=(new: <fieldtype>): Unit` is created if the field is var. Because the getter method has no parameter lists, its usage looks like a Java field access (`myObject.myProperty`), though it isn't. Scala also introduces sugar for methods that end in `_=`, allowing them to be called with `myObject.myProperty = newValue` notation. This is the same as `myObject.myProperty_=(newValue)`. You can manually create methods like this and see the same behavior. (Caveat: a manually defined method `x_=` will not sugar unless a getter`x` is also present.)

The function of (Boolean)BeanProperty is to simply add aliases to these methods named in the standard Java Bean way (getX/isX and setX). Therefore, they are unnecessary for pure Scala, but are useful if you need to conform to the Java standard for some reason. E.g. you use some library that reflectively accesses a bean's properties.

