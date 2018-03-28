---
layout: post
title: "eachElementSquared.js"
categories: dev
tags: algo
---

#### 반복문(for loop) + 배열(array) 알고리즘 문제

<br>

## problem

Complete the function '`eachElementSquared`'

that accepts an array and returns

a new array of each element squared.

<br>

> square: 제곱

<br>

## solution 01

```javascript
const array = [3, 2, 7, 5];

function eachElementSquared(array) {
   for (let i = 0; i < array.length; i++) {
      array[i] *= array[i];
   }
   return array;
}


eachElementSquared(array);	// [9, 4, 49, 25]
```

<br>

## solution 02

```javascript
const array = [3, 2, 7, 5];

function eachElementSquared(array) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      result.push(array[i] * array[i]);
   }
   return result;
}


eachElementSquared(array);	// [9, 4, 49, 25]
```

<br>

## solution 03

```javascript
const array = [3, 2, 7, 5];

function eachElementSquared(array) {
   let result = [];
   
   for (let i of array) {
      result.push(i * i);
   }
   return result;
}


eachElementSquared(array);	// [9, 4, 49, 25]
```

<br>

## solution 04

```javascript
const array = [3, 2, 7, 5];

function eachElementSquared(array) {
   return array.map((a) => { return a * a });
}


eachElementSquared(array);	// [9, 4, 49, 25]
```

