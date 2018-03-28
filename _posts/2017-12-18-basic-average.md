---
layout: post
title: "average.js"
categories: dev
tags: algo
---

#### 반복문(for loop) + 배열(array) 알고리즘 문제

<br>

## problem

Write a function called '`average`'

that takes an array of numbers as a parameter

and returns the average of those numbers.

<br>

## solution 01

```javascript
function average(array) {
   let result = 0;
   
   for (let i = 0; i < array.length; i++) {
      result += array[i];
   }
   return result / array.length;
}


average([1, 2, 3, 4]);	// 2.5
```

<br>

## solution 02

```javascript
function average(array) {
   let result = 0;
   
   for (let i of array) {
      result += i;
   }
   return result / array.length;
}


average([1, 2, 3, 4]);	// 2.5
```

<br>

## solution 03

```javascript
function average(array) {
   let result = array.reduce((a, b) => { return a + b });
   return result / array.length;
}


average([1, 2, 3, 4]);	// 2.5
```

