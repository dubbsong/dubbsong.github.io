---
layout: post
title: "cons.js"
categories: dev
tags: algo
---

#### 배열(array) 알고리즘 문제

<br>

## problem

Complete the function '`cons`'

that accepts an element and an array,

and returns an array with the element added

to the front of the array.

<br>

> var fruits = ['Banana', 'Apple'];
>
> fruits.unshift('Lemon', 'Orange');
>
> // ['Lemon', 'Orange', 'Banana', 'Apple']

<br>

## solution 01

```javascript
const array = [3, 2, 7, 5];


function cons(x, array) {
   array.unshift(x);
   return array;
}


cons([4, 4], array);	// [[4, 4], 3, 2, 7, 5]
```

<br>

## solution 02

```javascript
const array = [3, 2, 7, 5];


function cons(x, array) {
   return [x, ...array];
}


cons([4, 4], array);	// [[4, 4], 3, 2, 7, 5]
```

