---
layout: post
title: "pickElements.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a JavaScript function

to get the first element of an array.

<br>

Passing a parameter '`n`' will return

the first n elements of the array.

<br>

If '`n === 0`' return an empty array.

<br>

## solution 01

```javascript
const array = ['a', 'b', 'c', 'd'];


function pickElements(array, n) {
   if (n === 0) {
      return [];
   } else if (n === undefined) {
      return array.slice(0, 1);
   } else {
      return array.slice(0, n);
   }
}


pickElements(array);	// ['a']
pickElements(array, 0);	// []
pickElements(array, 2);	// ['a', 'b']
```

<br>

## solution 02

```javascript
const array = ['a', 'b', 'c', 'd'];


function pickElements(array, n) {
   return array.slice(0, typeof n === 'number' ? n : 1);
}


pickElements(array);	// ['a']
pickElements(array, 0);	// []
pickElements(array, 2);	// ['a', 'b']
```

