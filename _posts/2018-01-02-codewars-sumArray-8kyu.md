---
layout: post
title: "sumArray.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 배열(array) 알고리즘 문제

<br>

## problem

Write a method sum

that takes an array of numbers

and returns the sum of the numbers.

<br>

The numbers can also be negative.

If the array does not contain any numbers

then you should return 0.

<br>

## solution 01

```javascript
function sumArray(numbers) {
   let result = 0;
   
   for (let i = 0; i < numbers.length; i++) {
      result += numbers[i];
   }
   return result;
}


sumArray([]);			 // 0
sumArray([1, 2.4, 4, -1]);	// 6.4
```

<br>

## solution 02

```javascript
function sumArray(numbers) {
   return numbers.reduce((a, b) => a + b, 0);
}


sumArray([]);			 // 0
sumArray([1, 2.4, 4, -1]);	// 6.4
```

