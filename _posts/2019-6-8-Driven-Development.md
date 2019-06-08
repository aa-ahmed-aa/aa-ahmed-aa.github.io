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
# Driven Development
> As i would like to describe it driven development is the twist between developers and business guys that makes them survive together to translate the requirements into a software features in an organized flow.

<div class="breaker"></div>

# TDD
<div class="side-by-side">
    <div class="toleft" style="padding-left: 15%;margin-right: -13%;">
        <img width="50%" class="image" src="https://aa-ahmed-aa.github.io/assets/tddSteps.jpg" alt="TDD Steps">
        <figcaption class="caption">TDD Steps</figcaption>
    </div>
    <div class="toright">
        <p>TDD can be defined as a programming practice that instructs developers to write new code only if an automated test has failed. This avoids duplication of code. TDD means "Test Driven Development". The primary goal of TDD is to make the code clearer, simple and bug-free.</p>
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
BDD lets us develop, test and think about the code from the view of the business owner.

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

<style>
h1 {
    font-size: 50px;
}
</style>