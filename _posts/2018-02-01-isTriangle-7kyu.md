---
layout: post
title: "isTriangle.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 기본 수학 알고리즘 문제

<br>

## problem

Implement a method

that accepts 3 integer values `a`, `b`, `c`.

<br>

The method should return true

if a triangle can be built

with the sides of given length and false

in any other case.

<br>

In this case,

all triangles must have surface

greater than 0 to be accepted.

<br>

## solution 01

```javascript
function isTriangle(a, b, c) {
   return a + b > c && a + c > b && b + c > a;
}


isTriangle(1, 2, 2);	// true
isTriangle(6, 2, 2);	// false
```

<br>

## solution 02

```javascript
function isTriangle(a, b, c) {
   const max = Math.max(a, b, c);
   return a + b + c - max > max;
}


isTriangle(1, 2, 2);	// true
isTriangle(6, 2, 2);	// false
```

<br>

## solution 03

```javascript
const isTriangle = (a, b, c) => Math.max(a, b, c) < (a + b + c) / 2;


isTriangle(1, 2, 2);	// true
isTriangle(6, 2, 2);	// false
```

