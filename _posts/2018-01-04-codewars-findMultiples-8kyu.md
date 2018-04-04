---
layout: post
title: "findMultiples.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) 알고리즘 문제

<br>

## problem

You will build a program that takes a value, '`integer`',

and returns a list of its multiples up to another value, '`limit`'.

<br>

If limit is a multiple of integer, it should be included as well.

The limit will always be higher than the base.

<br>

## solution

```javascript
function findMultiples(integer, limit) {
   let result = [];
   
   for (let i = integer; i <= limit; i += integer) {
      result.push(i);
   }
   return result;
}


findMultiples(5, 25);	// [5, 10, 15, 20, 25]
findMultiples(8, 10);	// [8]
```



