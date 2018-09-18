---
layout: post
title: "isDivisible.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) 알고리즘 문제

<br>

## problem

Create a function '`isDivisible`' that checks

if a number '`n`' is divisible

by two numbers '`x`' and '`y`'.

<br>

All inputs are positive, non-zero digits.

<br>

## solution 01

```javascript
function isDivisible(n, x, y) {
   if (n % x === 0 && n % y === 0) {
      return true;
   } else {
      return false;
   }
}


isDivisible(12, 3, 4);	// true
isDivisible(13, 3, 4);	// false
```

<br>

## solution 02

```javascript
function isDivisible(n, x, y) {
   return n % x === 0 && n % y === 0;
}


isDivisible(12, 3, 4);	// true
isDivisible(13, 3, 4);	// false
```

<br>

## solution 03

```javascript
const isDivisible = (n, x, y) => n % x === 0 && n % y === 0;


isDivisible(12, 3, 4);	// true
isDivisible(13, 3, 4);	// false
```

