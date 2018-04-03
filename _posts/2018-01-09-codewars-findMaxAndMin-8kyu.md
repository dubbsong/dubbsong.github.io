---
layout: post
title: "findMaxAndMin.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 조건문(if) + 배열(array) 알고리즘 문제

<br>

## problem

Your task is to make two function, '`max`', '`min`'

that take a(n) array/vector of integers list as input and outputs,

respectively, the largest and lowest number

in that array/vector.

<br>

## solution 01

```javascript
function max(array) {
   let maxNum = array[0];
   
   for (let i = 0; i < array.length; i++) {
      if (maxNum < array[i]) {
         maxNum = array[i];
      }
   }
   return maxNum;
}



function min(array) {
   let minNum = array[0];
   
   for (let i = 0; i < array.length; i++) {
      if (minNum > array[i]) {
         minNum = array[i];
      }
   }
   return minNum;
}


max([-2, -1, 0, 1, 2]);	// 2
min([-2, -1, 0, 1, 2]);	// -2
```

<br>

## solution 02

```javascript
function max(array) {
   array.sort((a, b) => b - a);
   return array[0];
}



function min(array) {
   array.sort((a, b) => a - b);
   return array[0];
}


max([-2, -1, 0, 1, 2]);	// 2
min([-2, -1, 0, 1, 2]);	// -2
```

<br>

## solution 03

```javascript
const max = array => array.sort((a, b) => b - a)[0];
const min = array => array.sort((a, b) => a - b)[0];


max([-2, -1, 0, 1, 2]);	// 2
min([-2, -1, 0, 1, 2]);	// -2
```

<br>

## solution 04

```javascript
const max = array => Math.max(...array);
const min = array => Math.min(...array);


max([-2, -1, 0, 1, 2]);	// 2
min([-2, -1, 0, 1, 2]);	// -2
```

