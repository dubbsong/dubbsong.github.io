---
layout: post
title: "extend2.js"
categories: dev
tags: algo
---

#### 객체(object) 활용 알고리즘 문제

<br>

## problem

Write a function called '`extend2`'.

<br>

Given two objects,

'extend2' adds properties

from the 2nd object to the 1st object.

<br>

> Notes:
>
> Add any keys that are not in the 1st object.
>
> If the 1st object already has a given key, ignore it.
>
> Do not modify the 2nd object at all.

<br>

## solution

```javascript
let obj1 = { a: 1, b: 2 };
let obj2 = { b: 4, c: 3 };

function extend2(obj1, obj2) {
   for (let i in obj2) {
      obj1[1] = obj1[i] || obj2[i];
   }
   return obj1;
}


extend2(obj1, obj2);	// { a: 1, b: 2, c: 3 }
```

