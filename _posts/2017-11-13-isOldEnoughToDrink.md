---
layout: post
title: "isOldEnoughToDrink.js"
categories: dev
tags: algo
---

#### 조건문 + boolean 알고리즘 문제

<br>

## problem

Write a function called '`isOldEnoughToDrink`'.

Given a number, in this case an age,

'isOldEnoughToDrink' returns whether a person

of this given age is old enough to legally drink

in the United States.

\* <u>The legal drinking age in the United States is 21.</u>

<br>

## solution 01

```javascript
function isOldEnoughToDrink(age) {
   if (age >= 21) {
      return true;
   } else {
      return false;
   }
}


isOldEnoughToDrink(21);		// true
isOldEnoughToDrink(20);		// false
```

<br>

## solution 02

```javascript
function isOldEnoughToDrink(age) {
   return age >= 21 ? true : false;
}


isOldEnoughToDrink(21);		// true
isOldEnoughToDrink(20);		// false
```



