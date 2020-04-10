---
layout: post
title:  "Comparator and Comparable"
image: ''
date:   2020-04-10 11:30:00 +0800
tags:
- java
description: ''
categories:
- Learn Java 
---

Comparable and Comparator are two interface provided by Java to sort objects using the properties of a class.

<h1>Comparable</h1>

This interface provide an ordering on the objects of each class that implements it. This ordering is called as the class's natural ordering, and the class's ```compareTo``` method is referred to as its natural comparison method.

``` 
public interface Comparable<T>
``` 

Example :






|                          Comparable                           |                Comparator                |
|---------------------------------------------------------------|------------------------------------------|
| java.lang.Comparable                                          | java.util.Comparator                     |
| int objOne.compareTo(objTwo)                                  | int compare(objOne, objTwo)              |
| Negative, if objOne < objTwo<br/>Zero,  if objOne == objTwo <br/>Positive,  if objOne > objTwo  |    Same as Comparable                                            |
|  You must modify the clas whose  instances you want to sort.  | You build a class separate from to sort the class whose instances you want |
| Only one sort sequemce can be created                         | Many sort sequences can be created       |
| Implemented frequently in the API by:<br/>String, Wrapper classes, Date, Calandar                         | Meant to be implemented to sort<br/>instances of third-party classes.          |


