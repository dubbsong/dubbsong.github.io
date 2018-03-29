---
layout: post
title: "cleanAnObject.js"
categories: dev
tags: algo
---

#### 객체(object) + 반복문(for loop) + 조건문(if) 알고리즘 문제

<br>

## problem

The following object has a number of key/value pairs

that need to be removed:

```javascript
var dirtyObject = {
   _fht: 192492,
   name: 'Sam D. Azor',
   age: 28,
   _byz: 939205,
   _ttrs: 510852
}
```

<br>

The function '`cleanAnObject`' should accept an object

as an argument and return a new object

that has all of the key/value pairs of its parameter

except for those that begin with.

<br>

## solution

```javascript
var dirtyObject = {
   _fht: 192492,
   name: 'Sam D. Azor',
   age: 28,
   _byz: 939205,
   _ttrs: 510852
}



function cleanAnObject(object) {
   for (let i in object) {
      if (i[0] === '_') {
         delete object[i];
      }
   }
   return object;
}


cleanAnObject(dirtyObject);	// { name: 'Sam D. Azor', age: 28 }
```

