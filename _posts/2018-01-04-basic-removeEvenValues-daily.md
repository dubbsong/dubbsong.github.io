---
layout: post
title: "removeEvenValues.js"
categories: dev
tags: algo
---

#### 객체(object) 활용 알고리즘 문제

<br>

## problem

Write a function called '`removeEvenValues`'.

<br>

Given any object,

'removeEvenValues' removes any properties

whose values are even numbers.

<br>

Do this in place and return the original object,

do not construct a cloned object that omits the properties.

<br>

## solution 01

```javascript
let obj = { a: 2, b: 3, c: 4 };

function removeEvenValues(obj) {
   for (let i in obj) {
      if (obj[i] % 2 === 0) {
         delete obj[i];
      }
   }
   return obj;
}


removeEvenValues(obj);	// { b: 3 }
```

<br>

## solution 02

```javascript
let obj = { a: 2, b: 3, c: 4 };

function removeEvenValues(obj) {
   for (let i in obj) {
      if (!(obj[i] % 2)) {
         delete obj[i];
      }
   }
   return obj;
}


removeEvenValues(obj);	// { b: 3 }
```

