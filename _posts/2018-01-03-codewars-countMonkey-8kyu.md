---
layout: post
title: "countMonkey.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) 알고리즘 문제

<br>

## problem

Given the number 'n',

populate an array with all numbers up to

and including that number,

but excluding zero.

<br>

## solution 01

```javascript
function countMonkey(n) {
   let result = [];
   
   for (let i = 0; i <= n; i++) {
      result.push(i);
   }
   return result;
}


countMonkey(4);	// [1, 2, 3, 4]
countMonkey(5);	// [1, 2, 3, 4, 5]
```

<br>

## solution 02

```javascript
function countMonkey(n) {
   return Array.from({length: n}, (_, i) => i + 1);
}


countMonkey(4);	// [1, 2, 3, 4]
countMonkey(5);	// [1, 2, 3, 4, 5]
```

