---
layout: post
title: "calAverage.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 배열(array) 알고리즘 문제

<br>

## problem

Write a function average

which calculates average of numbers

in given list.

<br>

## solution 01

```javascript
function calAverage(array) {
   let result = 0;
   
   for (let i = 0; i < array.length; i++) {
      result += array[i];
   }
   return result / array.length;
}


calAverage([1, 2, 3, 4]);	// 2.5
```

<br>

## solution 02

```javascript
function calAverage(array) {
   let result = array.length((a, b) => a + b, 0);
   return result / array.length;
}


calAverage([1, 2, 3, 4]);	// 2.5
```

<br>

## solution 03

```javascript
const calAverage = array => array.reduce((a, b) => a + b, 0) / array.length;
```

