---
layout: post
title:  "Hibernate interview questions"
image: ''
date:   2020-04-13 11:30:00 +0800
tags:
- hibernate
description: ''
categories:
- Learn Hibernate
---


<b>1) What is hibernate ?</b>

Hibernate is a Java framework that simplifies the development of Java application to interact with the database. It is an open source, lightweight, ORM (Object Relational Mapping) tool. Hibernate implements the specifications of JPA (Java Persistence API) for data persistence.

<b>2) What is JPA?</b>

Java Persistence API (JPA) is a Java specification that provides certain functionality and standard to ORM tools. The javax.persistence package contains the JPA classes and interfaces.

<b>2) get() vs load() method?</b>


| Sl No |          Key           |                                                        get()                                                         |                                   load()                                   |
|-------|------------------------|----------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------|
|     1 | Basic                  | It  is used to fetch data from the database for the given identifier                                                 | It  is also used to fetch data from the database for the given identifier  |
|     2 | Null Object            | It object not found for the given identifier then it will return null object                                         | It will throw object not found exception i.e ObjectNotFoundException       |
|     3 | Lazy or Eager loading  | It returns fully initialized object so this method eager load the object                                             | It always returns proxy object so this method is lazy load the object      |
|     4 | Performance            | It is slower than load() because it return fully initialized object which impact the performance of the application  | It is slightly faster.                                                     |
|     5 | Use Case               | If you are not sure that object exist then use get() method                                                          | If you are sure that object exist then use load() method                   |

Example:

If you are trying to load /get Empoyee object where empid=20. But assume that record is not available in database.

  ```
  Employee employee1 = session.load(Employee.class,20);  //Step-1
  System.out.println(employee1.getEmployeeId();       //Step-2  --Output =20
  System.out.println(employee1.getEmployeeName();       //Step-3 -->Output =ObjectNotFoundException
  ```
  
If you use load in step-1 hibernate won't fire any select query to fetch employee record from the database at this moment. At this point hibernate gives a dummy object (Proxy). This dummy object doesnt contain anything. It is new Employee(20). you can verify this in step-2 it will print 20. but in step-3 we are trying to find employee information. so at this time hibernate fires a sql query to fetch Empoyee objectr. If it is not found in DB.throws ObjectNotFoundException.

  ```Employee employee2 = session.get(Employee.class,20);  //Step-4  ```
  
For session.get() hibernate fires a sql query to fetch the data from db. so in our case id=20 not exists in DB. so it will return null.
