---
layout: post
title: "onlyEvenElements.js"
categories: dev
tags: algo
---

#### 반복문(for loop) + 조건문(if) + 배열(array) 알고리즘 문제

<br>

## problem

Given an array of numbers,

'`onlyEvenElements`' returns a new array

of just the even numbers.

<br>

## solution 01

```javascript
const array = [3, 2, 7, 5];


function onlyEvenElements(array) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      if (array[i] % 2 === 0) {
         result.push(array[i]);
      }
   }
   return result;
}


onlyEvenElements(array);	// [2]
```

<br>

## solution 02

```javascript
const array = [3, 2, 7, 5];


function onlyEvenElements(array) {
   let result = [];
   
   for (let i of array) {
      if (i % 2 === 0) {
         result.push[i];
      }
   }
   return result;
}


onlyEvenElements(array);	// [2]
```

