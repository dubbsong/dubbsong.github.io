---
layout: post
title: "select.js"
categories: dev
tags: algo
---

#### 반복문(for loop) + 조건문(if) + 객체(object) + 배열(array) 알고리즘 문제

<br>

## problem

Write a function '`select`'

that accepts two arguments:

an object and an array.

<br>

The array should contain names of keys

that will be selected from the object.

<br>

## solution 01

```javascript
const obj = { a: 4, b: 2, c: 9, d: 4 };


function select(object, array) {
   let result = {};
   
   for (let i = 0; i < array.length; i++) {
      if (object[array[i]]) {
         result[array[i]] = object[array[i]];
      }
   }
   return result;
}


select(obj, ['a']);		// { a: 4 }
select(obj, ['b', 'c']);	// { b: 2, c: 9 }
```

<br>

## solution 02

```javascript
const obj = { a: 4, b: 2, c: 9, d: 4 };


function select(object, array) {
   let result = {};
   
   for (let i of array) {
      if (object.hasOwnProperty(i)) {
         result[i] = object[i];
      }
   }
   return result;
}


select(obj, ['a']);		// { a: 4 }
select(obj, ['b', 'c']);	// { b: 2, c: 9 }
```

