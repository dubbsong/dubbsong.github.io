---
layout: post
title: "remove.js"
categories: dev
tags: algo
---

#### 반복문(for loop) + 조건문(if) + 배열(array) 알고리즘 문제

<br>

## problem

Write a function '`remove`'

that accepts an array and an element and returns

an array with all occurrences of element removed.

<br>

## solution 01

```javascript
function remove(array, element) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      if (array[i] !== element) {
         result.push(array[i]);
      }
   }
   return result;
}


remove([4, 2, 9, 4], 4);	// [2, 9]
remove([8, 6, 8, 8], 8);	// [6]
```

<br>

## solution 02

```javascript
function remove(array, element) {
   let result = [];
   
   for (let i of array) {
      if (i !== element) {
         result.push(i);
      }
   }
   return result;
}


remove([4, 2, 9, 4], 4);	// [2, 9]
remove([8, 6, 8, 8], 8);	// [6]
```

