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

<h2>Comparable Interface</h2>

This interface provide an ordering on the objects of each class that implements it. This ordering is called as the class's natural ordering, and the class's ```compareTo``` method is referred to as its natural comparison method.

``` public interface Comparable<T>``` 

Suppose a company have list of employees and we need to sort these employees by thier id. Consider that employee have properties id, name, age and date of join.
First we need to create a class ```Employee``` and implemnet with ```Comparable<Employee>``` then override the method ```compareTo```.

Employee POJO class:
'''
public class Employee implements Comparable<Employee>{

	
	public Employee(Integer id, String name, Integer age, String doj) {
		this.id = id;
		this.name = name;
		this.age = age;
		this.doj = doj;
	}
	
	private Integer id;
	private String name;
	private Integer age;
	String doj;
	
	public Integer getId() {
		return id;
	}
	public void setId(Integer id) {
		this.id = id;
	}
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public Integer getAge() {
		return age;
	}
	public void setAge(Integer age) {
		this.age = age;
	}
	public String getDoj() {
		return doj;
	}
	public void setDoj(String doj) {
		this.doj = doj;
	}
	@Override
	public int compareTo(Employee employee) {
		// TODO Auto-generated method stub
		return this.id - employee.id;
	}
	
	
}
'''




 

|                          Comparable                           |                Comparator                |
|---------------------------------------------------------------|------------------------------------------|
| java.lang.Comparable                                          | java.util.Comparator                     |
| int objOne.compareTo(objTwo)                                  | int compare(objOne, objTwo)              |
| Negative, if objOne < objTwo<br/>Zero,  if objOne == objTwo <br/>Positive,  if objOne > objTwo  |    Same as Comparable                                            |
|  You must modify the clas whose  instances you want to sort.  | You build a class separate from to sort the class whose instances you want |
| Only one sort sequemce can be created                         | Many sort sequences can be created       |
| Implemented frequently in the API by:<br/>String, Wrapper classes, Date, Calandar                         | Meant to be implemented to sort<br/>instances of third-party classes.          |


