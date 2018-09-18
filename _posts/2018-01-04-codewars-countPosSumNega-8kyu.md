---
layout: post
title: "countPosSumNega.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 조건문(if) 알고리즘 문제

<br>

## problem

Given an array of integers.

Return an array,

where the first element is the count of positive numbers

and the second element is sum of negative numbers.

<br>

## solution 01

```javascript
const array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, -11, -12, -13, -14, -15];


function countPosSumNega(array) {
   let positive = 0;
   let negative = 0;
   
   for (let i = 0; i < array.length; i++) {
      if (array[i] > 0) {
         positive += 1;
      } else {
         negative += array[i];
      }
   }
   return [positive, negative];
}


countPosSumNega(array);	// [10, -65]
```

<br>

## solution 02

```javascript
const array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, -11, -12, -13, -14, -15];


function countPosSumNega(array) {
   let positive = 0;
   let negative = 0;
   
   for (let i = 0; i < array.length; i++) {
      array[i] > 0 ? positive++ : negative += array[i];
   }
   return [positive, negative];
}


countPosSumNega(array);	// [10, -65]
```

