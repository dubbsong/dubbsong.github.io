---
layout: post
title: "generateRandomInteger.js"
categories: dev
tags: algo
---

#### 조건문 + boolean 알고리즘 문제

<br>

## problem

Write a function called '`generateRandomInteger`'.

Given an integer,

'generateRandomInteger' returns a random integer

between 0 and n.

<br>

\* <u>The MDN references on Math.random,</u>

<u>may be very helpful in solving this problem.</u>

\* <u>If you are given a negative number,</u>

<u>your function should return false.</u>

\* <u>If you are given 0,</u>

<u>your function should return 0.</u>

<br>

> Math.floor(Math.random() * 10);	// between 0 and 9
>
> Math.floor(Math.random() * 11);	// between 0 and 10
>
> Math.floor(Math.random() * 10) + 1;	// between 1 and 10

<br>

## solution

```javascript
function generateRandomInteger(num) {
   if (num > 0) {
      return Math.floor(Math.random() * (num + 1));
   } else if (num === 0) {
      return 0;
   } else {
      return false;
   }
}


generateRandomInteger(42);	// could be between 1 and 42
generateRandomInteger(0);	// 0
generateRandomInteger(-19);	// false
```



