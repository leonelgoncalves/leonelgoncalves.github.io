---
layout: post
title: "Reduce. The black sheep"
comments: true
description: "A breef introduction on why to use reduce function and it's benefits"
keywords: "javascript, basic"
--- 

One of the worst things an application can have is suffering from poor performance. From huge loading times to annoying waiting screens every time an action is done, it´s just a showcase of something done not-quite-as-good.

This is a problem I have seen in web applications of all sizes, and, when in some cases is the back end's responsibility to try to improve the queries and send back the information as soon as posible, there are a lot of cases in which the data is not being correctly handled, causing huge waiting time to the users. Most developers think that they can do almost every thing they want with the data without thinking about the impact this is going to have when the application
is in production, but afterwards, they are the only ones to blame when the application crashes.

## THE WHITE SHEEPS

There's a whole world of built in utilities to handle arrays of data but for the sake of keeping this article short, let's focus on the most used ones (I'll talk about the other ones in the future) which are map, filter and forEach.

Let us take a look at a simple example.

```js
  let transformedUsers = users.map( item => ( {isValid: isValid(item),username: item.email})
                              .filter( item =>  isValidUser(item) );
```

Is not a hard to find scenario. Small transformation to the data and then only get the valid users. The previous example even when is going to work is far from efficient. We are iterating the entire array twice, the first time to to a transformation and then again to get only the valid users. If we have 1000000 users then this operation gets really heavy (and yes I know that you shouldn't be handling 100000 user but bear with me) is like we were iterating an array of 2000000.

A better way to do this would be using the forEach statement. The only issue with this is that we need to store or result in another variable. It would look something like: 

```js
let transformedUsers = [];

Users.forEach( item => {
  const temp = {isValid: isValid(item), username: item.email};
  if (isValidUser(temp)){
    // this is the most common scenario
    transformedUsers.push(temp);
    // a better way to this would be using concat or the spread operator
    // transformedUsers = [ temp, ...transformedUsers];
  }
});
```
There is still an even better way to takle this.

## REDUCE

[Reduce](https://goo.gl/bhOmvq) is a function that is not very popular. First, because it may be a little difficult to understand at first, and second because is not very well known. Luckily for us thanks to frameworks like [Redux](https://goo.gl/3qcH20) functions like this are being used. Nonetheless lots of people don't know this function and it's benefits.

So first I'm going to re-write the code above now using reduce

 ```js

let transformedUsers = Users.reduce( (result, current) => {
  const temp = {isValid: isValid(item), username: item.email};
  return isValidUser(temp) ? [ temp, ...result ] : result;
}, []);

```
So lets look at 3 key benefits.

  - **The code looks way cleaner:** We could even extract the inner function and reuse it in other parts of our code. This reduces the amount of time that we (or someone else) will have to invest in maintaining the code (and since 40%-80% of the software lifecycle is maintenance, this is really important). Is always cheaper to invest 1 hour doing a change than 2 hours understanding how can we add that same change.
  - **We are not mutating anything:** This might look as a small benefit, but working with immutable data makes the code easier to test, to debug and in some cases it could even improve the performance.
  - **Only one iteration:** This can be the most important benefit. If we are working with 1000000 registries, and each validation takes 0.0001 seconds, this operation will take 100 seconds, that's more than a minute each time we need to check that. Imagine that you are paying a manager $200 per hour and that he has to wait for 1 minute every time he checks his email, if he has to check it 2 times every 10 minutes, we are talking about
     
     - 12 times per hour = 12M.
     - 12M per hour = 96M = 1.6H
     - **TOTAL:** $320.

     You are paying him $320 for waiting... that's not good for business right?.

     ![Dilbert](/assets/images/posts/waiting-dilbert.jpg)

This is a simple example. Other cases like using filter and distinct, or map, filter, distinct, each time we run one of these functions we are iterating the whole array, and in huge arrays this can be really hurtful.