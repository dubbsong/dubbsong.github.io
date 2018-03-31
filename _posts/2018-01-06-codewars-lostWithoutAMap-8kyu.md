---
layout: post
title: "lostWithoutAMap.js (8kyu)"
categories: codewars
tags: Algotithm Codewars
---

#### 배열(array) 알고리즘 문제

<br>

## problem

Given and array of integers(array),

return the array with each value doubled.

<br>

For the beginner,

try to use the '`map`' method

it comes in very handy quite a lot

so is a good one to know.

<br>

## solution

```javascript
function map(array) {
   return array.map(n => n * 2);
}


map([2]);		// [4]
map([1, 2, 3, 4]);	// [2, 4, 6, 8]
```

