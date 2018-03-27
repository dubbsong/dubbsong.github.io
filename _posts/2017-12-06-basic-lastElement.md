---
layout: post
title: "lastElement.js"
categories: dev
tags: algo
---

#### 조건문(if) + 불린(boolean) + 배열(array) 알고리즘 문제

<br>

## problem

Write a function '`lastElement`'

that takes an array as an argument

and returns the last element in that array.

If the array is empty, return null.

<br>

## solution

```javascript
function lastElement(array) {
   return array[array.length - 1] || null;
}


lastElement([8, 6, 8, 8]);		// 8
lastElement(['ssup', 'bro', 8688]);	// 8688
lastElement([]);			// null
```

