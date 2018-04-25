---
layout: post
title: "extend.js"
categories: dev
tags: algo
---

#### 반복문(for loop) + 객체(object) 알고리즘 문제

<br>

## problem

Write a function '`extend`'

that accepts two objects as arguments

and extends all of the key/value pairs

of the second one to the first one.

<br>

## solution 01

```javascript
function extend(obj1, obj2) {
   for (let i in obj2) {
      obj1[i] = obj2[i];
   }
   return obj1;
}


extend({ a: 1 }, { b: 2 });			 // { a: 1, b: 2 }
extend({ a: 1, c: 3 }, { b: 2, c: 4 });		// { a: 1, c: 4, b: 2 }
```

<br>

## solution 02

```javascript
function extend(obj1, obj2) {
   return Object.assign({}, obj1, obj2);
}


extend({ a: 1 }, { b: 2 });			 // { a: 1, b: 2 }
extend({ a: 1, c: 3 }, { b: 2, c: 4 });		// { a: 1, c: 4, b: 2 }
```

