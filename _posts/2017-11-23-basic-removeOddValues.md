---
layout: post
title: "removeOddValues.js"
categories: dev
tags: algo
---

#### 객체(object) + 반복문(for loop) + 조건문(if) 알고리즘 문제

<br>

## problem

Write a function '`removeOddValues`'

that takes an object as an argument

and returns an object with all key/value pairs

removed for which the value holds an odd number.

<br>

You'll need to use the '`typeof`' operator

to first check that the value are numbers.

<br>

## solution

```javascript
const object = {
   a: 'ssup',
   b: 2,
   c: 3,
   d: 4
}



function removeOddValues(object) {
   for (let i in object) {
      if (typeof (object[i]) === 'number' && object[i] % 2 === 1) {
         delete object[i];
      }
   }
   return object;
}


removeOddValues(object);	// { a: 'ssup', b: 2, d: 4 }
```

