---
layout: post
title: "sumOfArray.js"
categories: dev
tags: algo
---

#### 반복문(for loop) + 배열(array) 알고리즘 문제

<br>

## problem

Complete the function '`sumOfArray`'

that accepts an array and returns the sum of all its elements.

Assume all elements are numbers.

<br>

## solution 01

```javascript
const array = [3, 2, 7, 5];


function sumOfArray(array) {
   let result = 0;
   
   for (let i = 0; i < array.length; i++) {
      result += array[i];
   }
   return result;
}


sumOfArray(array);	// 17
```

<br>

## solution 02

```javascript
const array = [3, 2, 7, 5];


function sumOfArray(array) {
   let result = 0;
   
   for (let i of array) {
      result += i;
   }
   return result;
}


sumOfArray(array);	// 17
```

<br>

## solution 03

```javascript
const array = [3, 2, 7, 5];


function sumOfArray(array) {
   return array.reduce((a, b) => { return a + b });
}


sumOfArray(array);	// 17
```

