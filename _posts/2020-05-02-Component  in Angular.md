---
layout: post
title:  "Angular Components"
image: ''
date:   2020-05-02 11:30:00 +0800
tags:
- angular
description: ''
categories:
- Learn Angular 
---

Comparable and Comparator are two interface provided by Java to sort objects using the properties of a class.

<h2>Components</h2>

Angular is built upon components. The starting point of an Angular app is the bootstrapping of the initial parent component, much like the HTML DOM tree that starts with an HTML element and then branches down from there.

![My helpful screenshot](/assets/img/ajudando-carregar.jpg)


Angular runs on a component tree model. After Angular loads the first component with the bootstrap call, it then looks within that component's HTML view and sees if it has any nested components. If so, Angular finds matches and runs the appropriate component code on those. This repeats for each component down the tree. A component in Angular is used to render a portion of HTML and provide functionality to that portion. It does this through a Component class in which you can define application logic for the component. For example, you can have a MediaItemComponent that can have a property named mediaItem that represents the data for a mediaItem. And that component can also have a method called onDeleteClick that can handle raising the delete mediaItem event. With each component in Angular, you can specify an HTML template, the markup that will get rendered. And through the use of the Component class and how Angular renders the component, you can display the data for the mediaItem property in your template. And Angular provides an easy syntax, known as the template syntax, to wire up to DOM events within your template. So you can wire up the click event on a button to the onDeleteClick method. You can even use components within components. This is where the component tree comes into play. Much like how you write HTML, creating nested elements within elements, you can build out your Angular apps by having components rendering components within their templates. Each component gets configured with a selector, which tells Angular what markup element tag to associate the Component class logic with. When you build a component in Angular, you are creating support for a new custom element for the DOM.

