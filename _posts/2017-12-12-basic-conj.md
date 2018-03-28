---
layout: post
title: "conj.js"
categories: dev
tags: algo
---

#### 배열(array) 알고리즘 문제

<br>

## problem

Complete the function '`conj`'

that accepts an array and an element,

and returns an array with the element added

to the end of the array.

<br>

> var fruits = ['Banana', 'Orange', 'Apple'];
>
> fruits.push('Kiwi');
>
> // ['Banana', 'Orange', 'Apple', 'Kiwi']

<br>

## solution 01

```javascript
const array = [3, 2, 7, 5];

function conj(array, x) {
   array.push(x);
   return array;
}


conj(array, [4, 4]);	// [3, 2, 7, 5, [4, 4]]
```

<br>

## solution 02

```javascript
const array = [3, 2, 7, 5];

function conj(array, x) {
   return [...array, x];
}


conj(array, [4, 4]);	// [3, 2, 7, 5, [4, 4]]
```

