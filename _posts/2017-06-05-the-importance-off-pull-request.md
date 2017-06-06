---
layout: post
title: "The Importance of Pull Request"
comments: true
description: "The Importance of Pull Request"
keywords: "pull request"
---

I have been a fan of the Pull Request model since I first met him 8 years ago. For me at beginning it was not only a nice way to work with, but also a huge opportunity to learn. Since sometime around 2015, I've been reviewing Pull Requests in almost all the jobs I’ve been in too, but I still like to ask my colleagues to review my code, since a fresh view into your code can provide great feedback, and, in worst case scenario I like to review my own code like if someone else did it.

During all of that time, I have seen many great Pull Requests, and some that needed some work (including in many cases my own).

Creating a pull request is not just submitting the code in which you have been working the last days to meet the company steps for it to be included in the project code base. We always have to have in mind that, when we create a pull request we are taking away time from another person (and ergo money from your company), so it is the duty of every developer to make his best effort to reduce this taken time as much as possible. (This doesn’t mean that doing pull request is bad for business, since it create a stronger code base and with this less bugs and happier customers)

In the end creating pull request produce better code quality, since it makes the developer not only to meet their own personal standards, but in some cases, the standards of 1 or 2 more people.

Still many developers out there do not understand the importance of this practice, the benefits of it and the down side of it. This can cause bad results (like bad code, bad integration with agile frameworks like scrum and in some cases even frustrated reviewers). Therefore, here is a small list of things that every developer should have in mind to create a good pull request.

### Make it small and often
Some time ago, I received an email to review a pull request that looked like this.

![Bad pull request]({{ site.url }}/assets/images/posts/pull-request.png)


So I took a deep breath and started my almost tow hour-long odyssey of reviewing I do not know how many days of work. At some point, I had to review a file 2 or 3 times because I found things being repeated across the code…

While reviewing the pull request I could only think about how many more time is the person going to spend doing the changes I am going to request… Let us do a simple math. Imagine that the code base of the previous pull request was the work of 10 days. I spent 2 hours doing the review plus an hour explaining why those changes were needed, 2 more days for the developer to implement them and we are going to be optimistic here and just spent 1 more hour reviewing it and everything was right (which in most cases it doesn’t).

 - Developer 1: 10 developing+ 2 fixing days = 12 days.
 - Reviewer: 2 + 1 + 1 = 4 hours..

If instead of doing a huge pull request at the end of 10 days of work, developer 1 had, create the pull request in day 2, the story would have gone in a different way… The reviewer would had spent maybe 15 minutes doing the review and 15 more minutes explaining it. And since developer 1 already know a little bit more he will not repeat the same error across the code… saving him 2 days of development and 1 day in fixing issue. Therefore, the time chart would have ended:

 - Developer 1: 8 developing + 2 fixing days = 10 days.
 - Reviewer: 15 + 15 + 15 = 45 hours.
 
We saved the company 2 days and 1 hour of salary. Which at a flat of 100$/hour it is 1700$.

So, it may sound counter intuitive, but making more and smaller pull requests is way better than doing huge and less.

### Make sure all tests pass
Assuming that the code base in question has automated tests, make sure all tests pass before submitting a Pull Request.

This should be understood, but I regularly receive Pull Requests where one or more tests are failing.

### Avoid cutom formatting
We all have personal preferences about how the code should look… Some like spaces others like tabs. However, when you are working with other people you should not change the formatting of the existing code to fit 'your' style.

Every line of code you change is going to show in the diff views, and even when some tools have options to ignore changes of white spaces, not everybody use these stools and there are still things that cannot be ignored.

So if you really feel the urge to change white spaces, move code around within files, change formatting or do any other changes to the code, please add a message in the pull request specifying this, or if it is a mayor refactor create a new pull request with just these changes.

### Make sure you do not have conflicts
Try to always pull or rebase from the master branch (or dev branch depending on your team) before raising a pull request. Raising a pull request for it just been sent back or marked as “work needed” is one of the worst things you can do to a fellow developer

### Make sure the code builds and works!
Before submitting a Pull Request, build it on your own machine. True, works on my machine isn't particularly useful, but it's a minimum bar. If it doesn't work on your machine, it's unlikely to work on other machines as well.

After the code is compiled it is really important to check that it is working… specially when working with scripting languages is important to check that the code is working… more than one I’ve reviewed a pull request and when I tried to open the page this one stays in blank…

### Document your reasoning
Yes, code comments are (in most cases) code smells, and I definitely prefer nicely-named operations, types, and values over comments. Still, when writing code, you often have to make decisions that aren't self-evident (particularly when dealing with Business 'Logic').

Document why you wrote the code in the way you did; not what it does.

My preferred priority is this:

 - Self-documenting code: This is the most important thing every developer should know and Clean Code is literally a MUST TO for all working in this area.
 - Code comments: If there is no way (which almost never should happen) for you to make you code understandable (let us say that you have to transform some hard business stuff), add small comments in the code. This should not be longer than 2 lines and should be IN the code for them to persist across versions.
 - Commit messages: Almost all version control systems allow you to add descriptions. So if you are following some agile base rules and you are doing small commits, you can add explain why and what you did it the why you did. Most people do not use this tool, which is a shame since there are several tools that allow to auto generate release notes based on these comments. In addition, most companies do not really care about this, which cause them to do more work in the end. Is always better to have strong development rules that all developers have to follow and then have a nice auto generated release documentation, than make your senior developer (whom you are paying more) to spend 4 hours writing them.
 - Pull Request comments: If you need to explain something that does not belong to any of the previous mentioned cases, you can make a quick description in the pull request message. Here you can mention that only style were changed (white spaces and moving code around). This are going to be mainly temporary comments that are only relevant in short term.

You do not need to explain the obvious, but do consider erring on the side of caution. What is obvious to you today may not be obvious to anyone else or to you in three months.