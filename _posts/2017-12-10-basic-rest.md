---
layout: post
title: "rest.js"
categories: dev
tags: algo
---

#### 배열(array) 알고리즘 문제

<br>

## problem

Write a function '`rest`'

that returns all the elements in the array

except for the first one.

<br>

## solution

```javascript
const array = [3, 2, 7, 5];

function rest(array) {
   return array.slice(1, array.length);
}


rest(array);	// [2, 7, 5]
```

