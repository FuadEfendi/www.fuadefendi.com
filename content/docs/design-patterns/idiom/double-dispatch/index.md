---
title: Double Dispatch
categories:
  - Idiom
language: en
tags:
  - Extensibility
type: docs
---

## Intent
Double Dispatch pattern is a way to create maintainable dynamic
behavior based on receiver and parameter types.

## Class diagram
![alt text](etc/double-dispatch.png "Double Dispatch")

## Applicability
Use the Double Dispatch pattern when

* the dynamic behavior is not defined only based on receiving object's type but also on the receiving method's parameter type.

## Real world examples

* [ObjectOutputStream](https://docs.oracle.com/javase/8/docs/api/java/io/ObjectOutputStream.html)
