---
layout: post
title: "getMax.js"
categories: dev
tags: algo
---

#### 조건문(if) + 불린(boolean) 알고리즘 문제

<br>

## problem

Write a function called '`getMax`'.

Given two numbers,

'getMax' returns the larger of these two numbers.

\* <u>If the two numbers are equal, return either one.</u>

<br>

## solution 01

```javascript
function getMax(num1, num2) {
   if (num1 > num2) {
      return num1;
   } else {
      return num2;
   }
}


getMax(19, 34);		// 34
getMax(2.3, -19);	// 2.3
```

<br>

## solution 02

```javascript
function getMax(num1, num2) {
   return num1 > num2 ? num1 : num2;
}


getMax(19, 34);		// 34
getMax(2.3, -19);	// 2.3
```

<br>

## solution 03

```javascript
function getMax(num1, num2) {
   return Math.max(num1, num2);
}


getMax(19, 34);		// 34
getMax(2.3, -19);	// 2.3
```

