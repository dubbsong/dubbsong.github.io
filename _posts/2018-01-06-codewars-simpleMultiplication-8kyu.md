---
layout: post
title: "simpleMultiplication.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 불린(boolean) 알고리즘 문제

<br>

## problem

This kata is about multiplying a given number

by eight if it is an even number

and by nine otherwise.

<br>

## solution 01

```javascript
function simpleMultiplication(number) {
   if (number % 2 === 0) {
      return number * 8;
   } else {
      return number * 9;
   }
}


simpleMultiplication(1);	// 9
simpleMultiplication(2);	// 16
simpleMultiplication(3);	// 27
```

<br>

## solution 02

```javascript
function simpleMultiplication(number) {
   return number * (number % 2 ? 9 : 8);
}


simpleMultiplication(1);	// 9
simpleMultiplication(2);	// 16
simpleMultiplication(3);	// 27
```

<br>

## solution 03

```javascript
const simpleMultiplication = number => number * (number % 2 ? 9 : 8);


simpleMultiplication(1);	// 9
simpleMultiplication(2);	// 16
simpleMultiplication(3);	// 27
```

