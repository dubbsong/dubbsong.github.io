---
layout: post
title: "oddToEven.js"
categories: dev
tags: algo
---

#### 조건문(if) + 불린(boolean) + 배열(array) 알고리즘 문제

<br>

## problem

Write a function that takes an array

as an argument and returns the same array

except any odd numbers have been doubled.

<br>

## solution 01

```javascript
function oddToEven(array) {
   for (let i = 0; i < array.length; i++) {
      if (array[i] % 2 === 1) {
         array[i] *= 2;
      }
   }
   return array;
}


oddToEven([1, 2, 3, 4, 5]);	// [2, 2, 6, 4, 10]
```

<br>

## solution 02

```javascript
function oddToEven(array) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      if (array[i] % 2 === 1) {
         result.push(array[i] * 2);
      } else {
         result.push(array[i]);
      }
   }
   return result;
}


oddToEven([1, 2, 3, 4, 5]);	// [2, 2, 6, 4, 10]
```

<br>

## solution 03

```javascript
function oddToEven(array) {
   let result = [];
   
   for (let i of array) {
      i % 2 === 1 ? result.push(i * 2) : result.push(i);
   }
   return result;
}


oddToEven([1, 2, 3, 4, 5]);	// [2, 2, 6, 4, 10]
```

