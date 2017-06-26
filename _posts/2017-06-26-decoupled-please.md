---
layout: post
title: "How'd you like your code? Decoupled please."
comments: true
description: "Why is always better to invest time in having a decoupled code base."
keywords: "programming, decoupled, good practices"
--- 

![Decopled](/assets/images/posts/decoupled-please.jpg)

If I had a dollar for each time I've said "why on earth is this so highly coupled!?" I don't think I would be a millionaire, but I am sure I would already have at least two apartments and a couple of cars.

Most people don't notice (or don't know) the importance of maintaining the code as decoupled as possible. The amount of time and money that can be saved by doing this is amazing! However, for most people, thinking about how they can decouple and improve their code, is just a waste of time. Managers don't seem to care if the code is maintainable or not, in most cases they just want to meet a deadline (which in most cases is not even realistic due to bad planning) and that way they will look good with their bosses and stakeholders.

## Why decoupling code is SO important?

Adding a new feature or even doing regular maintenance to a code that is highly coupled most of the time is very difficult and introduces more bugs to the code. So is always better to invest a bit more time and have a nice a decoupled source code, than doing things fast and end up with a highly coupled code. Let us have a simple example.

Let us says that the time needed to add a new feature is 1 day of development and 4 hours of testing. However, if we want to add the same feature in a decoupled way it will take 1 day and half of development.

At first it may sound that is not worth the extra time. However, the software works almost as a living being, so changes, updates and upgrades are common requests. Taking into account that things change, maintaining highly-coupled code is hard, and adding new features becomes harder and harder as the code grows. I have seen developers take days to implement features that should have taken hours if the code was done well from the start.

Since adding features to a bad code base becomes harder each time, our balance could look something like this:

  - First feature:
    - Developer (coupled): 1 day. $100
    - Developer (decoupled): 1.5 day. $150
    - Tester: 1 day. $100
  - Second feature
    - Developer (coupled): 1.5 day. $150
    - Developer (decoupled): 1.5 day. $150
    - Tester: 1 day. $100
  - Third feature
    - Developer (coupled): 2.25 day. $225
    - Developer (decoupled): 1.5 day. $150
    - Tester (coupled): 1.5 day. $150
    - Tester (decoupled): 1 day. $100
  - Fourth feature
    - Developer (coupled): 4 day. $400
    - Developer (decoupled): 2 day. $200
    - Tester (coupled): 2 day. $200
    - Tester (decoupled): 1.5 day. $150
  - Total:
    - Coupled: $1425
    - Decoupled: $1150

    Therefore, in the end is going to be better if we have a decoupled code base. Now, I am going to explain briefly the two principles that (in my humble opinion) every developer should follow.

## Make pure functions

Creating dumb functions makes you code more reusable, readable, maintainable and easier to test. A pure function is a function which:
  - Given the same input, will always return the same output.
  - Produces no side effects.
  - Relies on no external mutable state.

Working with pure functions saves lots of time; I have spent up to 2 hours trying to find why and where a variable is changing. To, in the end, notice that somewhere along the call stack the variable (which is passed as a parameter) was changing as part of a validation in a service that had nothing to do with her in the beginning.

## Keep everything in the right place

There are two books that absolutely every programmer should read: The Clean Coder and Clean Code. They both agree that function should not be longer than 100 lines of code. If you have to scroll for a minute to reach the end of a class, by the time you reach the bottom you will no longer remember what you were looking for.

I once worked in a Java project in which at least two thirds of the classes were longer than 2000 lines of code and 400 lines functions. Each time something new was needed they had to spend at least 1 days just to find where in the code was supposed to go, and I am talking about senior developers here!