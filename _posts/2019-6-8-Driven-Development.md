---
title: "Driven Development"
layout: post
date: 2019-6-8 18:48
headerImage: false
tag:
- testing
- software engineering
star: true
category: blog
author: ahmedkhd
description: in this blog i will be taking about drived development TDD / BDD / DDD and the differences between them so get ready for an amazing topic.
---
> As i would like to describe it driven development is the twist between developers and business guys that makes them survive together to translate the requirements into a software features in an organized flow.

<div class="breaker"></div>

# TDD
<div class="side-by-side">
    <div class="toleft" style="padding-left: 15%;margin-right: -13%;">
        <img width="50%" class="image" src="https://aa-ahmed-aa.github.io/assets/tddSteps.jpg" alt="TDD Steps">
        <figcaption class="caption">TDD Steps</figcaption>
    </div>
    <div class="toright">
        <p>a short for test-driven-development, TDD can be defined as a programming practice that instructs developers to write new code only if an automated test has failed. This avoids duplication of code. TDD means "Test Driven Development". The primary goal of TDD is to make the code clearer, simple and bug-free.</p>
        <h4>Advantages of TDD</h4>
        <ul>
            <li>Early bug notification.</li>
            <li>Better Designed, cleaner and more extensible code.</li>
            <li>Confidence to Refactor</li>
        </ul>
    </div>
</div>

<div class="breaker"></div>

# BDD
a short for Behavior-driven-development, BDD lets us develop, test and think about the code from the view of the business owner.

## characteristics
- tests are writen ahead of the code like tdd.
- tests are more user-focused and based on the system’s behavior.

## Essentials to have in place before implementing BDD
- Requirements should be converted into user stories that can define concrete examples.
- Each example should be a valid user scenario, rather than a mere test case.
- An understanding of the __role-feature-reason__ matrix and the __given-when-then__ formula.
- An awareness of the need to write ‘the specification of the behavior of a class’ rather than ‘the unit test of a class’.

## Templates for writing BDD
### The ‘Given-When-Then’ formula BDD example
Given a certain scenario<br/>
When an action takes place<br/>
Then this should be the outcome.<br/>
#### Example
<img src="https://aa-ahmed-aa.github.io/assets/bdd_user_story.PNG" alt="bdd_user_story"/>

### Role-Feature-Reason matrix
This template is also used in BDD, in order to aid user story creation. This template is defined as:-

```
As a 
I want
So that

An example of such a user story would be: 
As a retail customer, 
I want to return an electronically purchase merchandise within 14 days, so that the refund will be processed
```


## benefits to using BDD
- You are no longer defining ‘test’, but are defining ‘behavior’.
- Better communication between developers, testers and product owners.
- Because BDD is explained using simple language, the learning curve will be much shorter.
- Being non-technical in nature, it can reach a wider audience.
- The behavioral approach defines acceptance criteria prior to development.



# TDD VS BDD

### Behavior __vs__ Test
__In TDD__ I don’t care much about the output. The only thing needed is to carry out the test in a particular way.
<br/>
__But in BDD__ I don’t mind how you come up with the output, only that the output has to be correct under the GIVEN condition.

### Communication and feedback
__In BDD__ you will come across a better specification since communication between the software developer and product owner is fast and easy.
<br/>
__TDD__ may lack the ability to specify the exact behavior, but you achieve higher quality with software code.

### Writing Failing Tests __vs__ Writing Failing Feature Tests.
__In BDD__, a test is written that can satisfy both the developer and customer, __but in TDD__ you write a test that will only satisfy a developer and the code they write. As can be seen below.


# DDD
a short for Domain-driven-development,DDD is a software development approach that uses and builds upon OOP(object opiented programming) principles and ideas, and now we have to ask two important questions.

## What is the Domain?
>The common dictionary definition of domain is: “A sphere of knowledge or activity.”

__Domain__ in the realm of software engineering commonly refers to the subject area on which the application is intended to apply. In other words, during application development, the domain is the __sphere of knowledge and activity around which the application logic revolves.__
<br>
Another common term used during software development is the __domain layer__ or __domain logic__, which may be better known to many developers as the __business logic__. The __business logic__ of an application refers to the higher-level rules for how __business objects__ interact with one another to create and modify modelled data.

## What is Domain-Driven Design?
is the expansion upon and application of the __domain__ concept, as it applies to the development of software. It aims to ease the creation of complex applications by connecting the related pieces of the software into an ever-evolving model.
#### DDD focuses on three core principles:
- Focus on the core __domain__ and __domain logic__.
- Base complex designs on models of the __domain__. 
- Constantly collaborate with __domain experts__, in order to improve the application model and resolve any emerging __domain__-related issues.

#### Terms defined by evan's book DDD
- __Context__: The setting in which a word or statement appears that determines its meaning. Statements about a model can only be understood in a context.
- __Model__: A system of abstractions that describes selected aspects of a domain and can be used to solve problems related to that domain.
- __Ubiquitous Language__: A language structured around the domain model and used by all team members to connect all the activities of the team with the software.
- __Bounded Context__: A description of a boundary (typically a subsystem, or the work of a specific team) within which a particular model is defined and applicable.

## Building Blocks of DDD
__Domain-driven design__ also defines a number of high-level concepts that can be used in conjunction with one another to create and modify __domain models__:
### Entity 
An __object__ that is identified by its consistent thread of continuity, as opposed to traditional __objects__, which are defined by their __attributes__.

### Value Object
An __immutable__ (unchangeable) __object__ that has __attributes__, but no distinct identity.

### Domain Event
 An object that is used to record a discrete event related to model activity within the system. While all events within the system could be tracked, a __domain event__ is only created for event types which the __domain experts__ care about.

### Aggregate
A cluster of __entities__ and __value objects__ with defined boundaries around the group. Rather than allowing every single __entity__ or __value object__ to perform all actions on its own, the collective __aggregate__ of items is assigned a singular __aggregate root__ item. Now, external objects no longer have direct access to every individual __entity__ or __value object__ within the __aggregate__, but instead only have access to the single __aggregate root__ item, and use that to pass along instructions to the group as a whole. This practice correlates with many of the actual coding practices we’re covering in our __design patterns__ series.

### Service
Essentially, a __service__ is an operation or form of business logic that doesn’t naturally fit within the realm of __objects__. In other words, if some functionality must exist, but it cannot be related to an __entity__ or __value object__, it’s probably a __service__.

### Repositories
Not be confused with common __version control repositories__, the __DDD__ meaning of a __repository__, __repository__ is a __service__ that uses a global interface to provide access to all __entities__ and __value objects__ that are within a particular __aggregate__ collection. Methods should be defined to allow for creation, modification, and deletion of objects within the __aggregate__. However, by using this __repository service__ to make data queries, the goal is to remove such data query capabilities from within the business logic of __object models__.

### Factories
As we’ve discussed through a number of __design patterns__ articles already, __DDD__ suggests the use of a __factory__, which encapsulates the logic of creating complex objects and __aggregates__, ensuring that the client has no knowledge of the inner-workings of object manipulation.


# Summery


> Domain-driven design also heavily emphasizes the ever-more-popular practice of continuous integration
<style>
h1 {
    font-size: 50px;
}
</style>