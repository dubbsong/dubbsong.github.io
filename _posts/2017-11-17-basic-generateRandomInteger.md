---
layout: post
title: "generateRandomInteger.js"
categories: dev
tags: algo
---

#### 조건문(if) + 불린(boolean) 알고리즘 문제

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


generateRandomInteger(0);	// 0
generateRandomInteger(-19);	// false
generateRandomInteger(42);	// could be between 1 and 42
```

> `Math.floor()` 메소드
>
> 가장 가까운 정수로 버림한 다음 결과를 반환한다.

<br>

> `Math.random()` 메소드
>
> 0(포함)과 1(제외) 사이의 난수(random number)를 반환한다.
>
> `Math.floor()` 메소드와 함께 사용해 임의의 정수를 반환할 수 있다.

<br>

> `Math.floor()` + `Math.random()`
>
> Math.floor(Math.random() * 10);	// between 0 and 9
>
> Math.floor(Math.random() * 11);	// between 0 and 10
>
> Math.floor(Math.random() * 10) + 1;	// between 1 and 10

<br>