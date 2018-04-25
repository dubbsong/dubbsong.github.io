---
layout: post
title: "butLast.js"
categories: dev
tags: algo
---

#### 배열(array) 알고리즘 문제

<br>

## problem

Write a function '`butLast`'

that returns all the elements in the array

except for the last one.

<br>

\* <u>Read about the `slice` method on MDN.</u>

<br>

> var fruits = ['Banana', 'Orange', 'Lemon', 'Apple'];
>
> var citrus = fruits.slice(1, 3);	// Orange, Lemon

<br>

## solution

```javascript
const array = [3, 2, 7, 5];


function butLast(array) {
   return array.slice(0, array.length - 1);
}


butLast(array.slice(0));	// [3, 2, 7]
butLast(array.slice(1));	// [2, 7]
butLast(array.slice(2));	// [7]
butLast(array.slice(0, 2));	// [3]


array.slice(0);		// [3, 2, 7, 5]
array.slice(0);		// [2, 7, 5]
array.slice(0);		// [7, 5]
array.slice(0, 2);	// [3, 2]
```



