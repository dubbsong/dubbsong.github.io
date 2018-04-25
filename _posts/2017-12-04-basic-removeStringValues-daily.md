---
layout: post
title: "removeStringValues.js"
categories: dev
tags: algo
---

#### 객체(object) 활용 알고리즘 문제

<br>

## problem

Write a function called '`removeStringValues`'.

<br>

Given an object,

'removeStringValues' removes any properties

on the given object whose values are strings.

<br>

## solution

```javascript
const obj = { name: 'Sam', age: 28 };

function removeStringValues(obj) {
   for (let i in obj) {
      if (typeof obj[i] === 'string') {
         delete obj[i];
      }
   }
   return obj;
}


removeStringValues(obj);	// { age: 28 }
```

