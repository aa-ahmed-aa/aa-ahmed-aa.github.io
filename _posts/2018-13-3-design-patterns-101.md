---
title: "Design patterns 101"
layout: post
date: 2018-3-13 06:48
headerImage: false
tag:
- DesignPattern
star: true
category: blog
author: ahmedkhd
description: In this blog i talk about design patterns from like a getting started 
tutorial to an advanced patterns you might see in many open source projects
---

### Table of Content

* Who is this blog for
* Before you start
* Quick Review
	1. S.O.L.I.D
	2. Dependency injection
	3. Composition and Aggregation
* Design Patterns
* Patterns in the real world


## Who is this blog for
* if you want to be a better programmer (reading others code - enhancing your skills).
* if you think of a scenario that your application is scaling up and you need to figure a solution to manage your business requirements .
* if you are repeating yourself when you write code (unintentionally).
* those who think design pattern is a black box and can't really know what is a design pattern.
* sometimes you see snippet of code that you don't understand in programming language 
that you have experience with and you wonder why is this code designed this way.

<div class="breaker"></div>

## Before you start
This blog is a brief of 14 design pattern in Head first design pattern, 
so to get the biggest benefit of this blog,
i recommend you follow these steps :-
1. Read the pattern definition.
2. Understand the problem introduced and try to imagine it in bigger scale.
3. Read the UML.
4. Trace the code example.

Two important things you need to know before we go further :-

#### First
Design pattern is just a clean way to solve a problem and provide flexibility to your code
not showing of your enhancement skills so if you though you have an idea of making a pattern better first thing is not 
think if your idea is applied by SOLID(we will come to this later in this blog) or not, think of SOLID as your brakes that will stop your fantasy.

#### Second
Patterns are not used separately from each others at the end of this blog you can use many patterns together like you will see in MVC.

This blog is based on [this repo](https://github.com/aa-ahmed-aa/Design_Pattern) 
so go ahead and star it.

<div class="breaker"></div>

## Quick Review

### S.O.L.I.D
 every letter stands for a specific word with a specific concepts so let's get started right away.

> #### S - Single-responsiblity principle
>> A class should have one and only one reason to change, meaning that a class should have only one job.

> #### O - Open-closed principle
>> Objects or entities should be open for extension, but closed for modification.

> #### L - Liskov substitution principle
>> Let q(x) be a property provable about objects of x of type T. Then q(y) should be provable for objects y of type S where S is a subtype of T.

> #### I - Interface segregation principle
>> A client should never be forced to implement an interface that it doesn't use or clients shouldn't be forced to depend on methods they do not use.

> #### D - Dependency Inversion Principle
>> Entities must depend on abstractions not on concretions. It states that the high level module must not depend on the low level module, but they should depend on abstractions.


* Note : you can find more information about solid and code examples [Here](https://scotch.io/bar-talk/s-o-l-i-d-the-first-five-principles-of-object-oriented-design).

### Dependency injection
we use this technique to provide more functionality to an object from another dependent objects.
#### Example
here we injected class A to class B.

{% highlight php %}
class A{
	public function show()
	{
		print "Hello from A Class";
	}
}

class B{
	public $A;
	
	public function __construct()
	{
		$this->A = new A();
	}
	
	public function showFromA()
	{
		print $this->A->show();
	}
	
}

$b = new B();
$b->showFromA();

{% endhighlight %}

### Composition and Aggregation
Composition is effectively an ownership relationship, while aggregation is a “contains” relationship. In composition, the parts can not exist outside the thing that contains them, but individual things can exist on their own as unique entities in aggregation.

#### in order to keep this blog short and sticky to the point i recommend you read this blog [Composition and aggregation](https://www.brainbell.com/tutorials/php/abstract-interface-composition-aggregation.html)

<div class="breaker"></div>

## Design Patterns
follow the link of every pattern to see pattern definition, UML, and code examples
> Do not forget to trace the code this is the most important step to get familiar with the pattern
### [Strategy pattern](https://github.com/aa-ahmed-aa/Design_Pattern/tree/master/Strategy%20pattern)
Defines a family of algorithms ,encapsulates each one and makes them interchangable. strategy lets the algorithm vary independently

### [Observer Pattern (Keeping your objects in the know) ](https://github.com/aa-ahmed-aa/Design_Pattern/tree/master/Observer%20pattern)
Defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.
> you may see this pattern used alot in the front-end framework because it needs to eep track of data synced to the UI.

### [Decorator Pattern (Decorating Objects) ](https://github.com/aa-ahmed-aa/Design_Pattern/tree/master/Decorator%20pattern)
Decorators provide a flexibile alternative to subclassing extending functionality.

### [Factory Pattern (Backing with oo Goodness)](https://github.com/aa-ahmed-aa/Design_Pattern/tree/master/Factory%20pattern)
Factory pattern divided into two main types (Factory method and Abstract factory), In this pattern i will focus on the difference between the two subset patterns and will code only the factory method.
>> Check the difference between **Abstract Factory** and **Factory Method**

### [Singleton Pattern (One of a kind object)](https://github.com/aa-ahmed-aa/Design_Pattern/tree/master/Singleton%20pattern)
Ensure that a class has one instance and provide a global point of access to it ,we can say that this pattern is our ticket to creating one-of-a-kind objects for which there is only one instance.

### [Command Pattern (Encapsulating Invocation)](https://github.com/aa-ahmed-aa/Design_Pattern/tree/master/Command%20pattern)
Encapsulates a request as an object, thereby letting you parameterize clients with different requests, queue or log requests, and support undoable operations.

### [Adapter Pattern](https://github.com/aa-ahmed-aa/Design_Pattern/tree/master/Adapter%20pattern)
Convert the interface of a class into another interface clients expect.let's classes work together that couldn't otherwise because of incompatible interfaces.
> Check the two adapter types 

### [Facade Pattern](https://github.com/aa-ahmed-aa/Design_Pattern/tree/master/Facade%20pattern)
Provides a unified interface to a set of interfaces in a subsystem facade defines a higher-level interface that makes the subsystem easier to use.


### [Template Method Pattern (Encapsulating Algorithms)](https://github.com/aa-ahmed-aa/Design_Pattern/tree/master/Template%20Method%20pattern)
Define the skeleton of an algorithm in an operation, deferring some steps to subclasses.Template Method lets subclasses redefine certain steps of an algorithm without changing the algorithm's structure.

### [Iterator Pattern](https://github.com/aa-ahmed-aa/Design_Pattern/tree/master/Iterator%20pattern)
Provide a way to access of an aggregation object sequentially without exposing it's underlying representation.

### [Composite Pattern](https://github.com/aa-ahmed-aa/Design_Pattern/tree/master/Composite%20pattern)
Compose objects into tree structured to request part whole hierarchies, Composite let's clients treat individual objects and compositions of objects uniformly.

### [Proxy Pattern](https://github.com/aa-ahmed-aa/Design_Pattern/tree/master/Proxy%20pattern)
Provide a surrogate or placeholder for another object to control access to it

### [State Pattern](https://github.com/aa-ahmed-aa/Design_Pattern/tree/master/State%20pattern)
Allow an object to alter its behavior when its internal state changes the object will appear to change its class.

<div class="breaker"></div>

## Patterns in the real world
Categorizing patterns will help us understand the difference between patterns and also will help us memorizing them.
#### Categorize patterns as (Structural - Behavioural - Creational)
> #### Structural
>> Decorator - Composite - Proxy - Facade - Adapter
> #### Behavioural
>> Template Method - Iterator - Command - Observer - State - Strategy
> #### Creational
>> Singleton - Abstract Factory - Factory Method

#### Categorize patterns that deals with (Class - Object)
> #### Class
>> Template Method - Adapter - Factory Method
> #### Object
>> Command - Decorator - Proxy - Composite - Facade - Iterator - Observer - Strategy - Singleton - State - Abstract Method 

#### Thinking in pattern
##### Keep it simple (KISS)
solve things in the simplest way possible, your goal should be simplicity, not "how should i apply a pattern".
##### Design patterns aren't a magic bullet; in fact, they're not even a bullet!
patterns aren't a magic bullet you can't plug one in, compile and then take an early lunch, to use patterns , you also need to think of the consequences for the rest of your design.

##### You know you need a pattern when...
once you're sure a simple solution will not meet your needs, you should consider the problem 
along with the set of constraints under which the solution will need to operate- these will help you match your problem to a pattern.
 