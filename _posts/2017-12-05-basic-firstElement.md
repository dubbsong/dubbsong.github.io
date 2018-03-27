---
layout: post
title: "firstElement.js"
categories: dev
tags: algo
---

#### 조건문(if) + 불린(boolean) + 배열(array) 알고리즘 문제

<br>

## problem

Write a function '`firstElement`'

that takes an array as an argument

and returns the first element in that array.

If the array is empty, return null.

<br>

## solution 01

```javascript
function firstElement(array) {
   if (array.length === 0) {
      return null;
   } else {
      return array[0];
   }
}


firstElement([8, 6, 8, 8]);		// 8
firstElement(['ssup', 'bro', 8688]);	// ssup
firstElement([]);			// null
```

<br>

## solution 02

```javascript
function firstElement(array) {
   return array[0] || null;
}


firstElement([8, 6, 8, 8]);		// 8
firstElement(['ssup', 'bro', 8688]);	// ssup
firstElement([]);			// null
```

<br>

## solution 03

```javascript
function firstElement(array) {
   if (!array.length) {
      return null;
   } else {
      return array[0];
   }
}


firstElement([8, 6, 8, 8]);		// 8
firstElement(['ssup', 'bro', 8688]);	// ssup
firstElement([]);			// null
```

