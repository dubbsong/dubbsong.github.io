---
layout: post
title: "nonConsecutive.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 조건문(if) 알고리즘 문제

<br>

## problem

Your task is to find the first element

of an array that is not consecutive.

<br>

If the whole array is consecutive

then return '`null`'.

<br>

The array will always have at least 2 elements

and all the elements will be numbers.

<br>

## solution

```javascript
function nonConsecutive(array) {
   for (let i = 0; i < array.length - 1; i++) {
      if (array[i] + 1 !== array[i + 1]) {
         return array[i + 1];
      }
   }
   return null;
}


nonConsecutive([1, 2, 4, 5]);	// 4
nonConsecutive([1, 2, 3, 5]);	// 5
```

