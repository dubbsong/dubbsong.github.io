---
layout: post
title: "reduceButGrow.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 배열(array) 알고리즘 문제

<br>

## problem

Given and array of integer(array),

return the result of multiplying the values

together in order.

<br>

For the beginner,

try to use the '`reduce`' method

it comes in very handy quite a lot

so is a good one to know.

<br>

Array will not be empty.

<br>

## solution

```javascript
function reduceButGrow(array) {
   return array.reduce((a, b) => a * b);
}


reduceButGrow([2, 3]);		// 6
reduceButGrow([2, 2, 2, 2]);	// 16
```

