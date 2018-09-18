---
layout: post
title: "sumSquares.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 배열(array) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

You are given a program '`sumSquares`'

that takes an '`array`' as input

and returns the sum of the squares

of each item in an array.

<br>

## solution 01

```javascript
function sumSquares(array) {
   let result = 0;
   
   for (let i = 0; i < array.length; i++) {
      result += array[i] * array[i];
   }
   return result;
}


sumSquares([2, 2]);	// 8
sumSquares([4, 4]);	// 32
```

<br>

## solution 02

```javascript
function sumSquares(array) {
   return array.reduce((a, b) => a + b * b, 0);
}


sumSquares([2, 2]);	// 8
sumSquares([4, 4]);	// 32
```

