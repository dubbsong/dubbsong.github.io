---
layout: post
title: "triangular.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) 알고리즘 문제

<br>

## problem

Triangular numbers are so called

because of the equilateral triangular shape

that they occupy when laid out as dots.

<br>

Example

> 1st(1)
>
> *

<br>

> 2nd(3)
>
> **
>
> *

<br>

> 3rd(6)
>
> \***
>
> **
>
> *

<br>

## solution 01

```javascript
function triangular(n) {
   let result = 0;
   
   for (let i = 0; i <= n; i++) {
      result += i;
   }
   return result;
}


triangular(1);	// 1
triangular(2);	// 3
triangular(3);	// 6
triangular(4);	// 10
```

<br>

## solution 02

```javascript
function triangular(n) {
   return n > 0 ? ((n * n) + n) / 2 : 0;
}


triangular(1);	// 1
triangular(2);	// 3
triangular(3);	// 6
triangular(4);	// 10
```

<br>

## solution 03

```javascript
function triangular(n) {
   return n > 0 ? n * (n + 1) / 2 : 0;
}


triangular(1);	// 1
triangular(2);	// 3
triangular(3);	// 6
triangular(4);	// 10
```

<br>

## solution 04

```javascript
function triangular(n) {
   if (n < 1) {
      return 0;
   } else if (n === 1) {
      return 1;
   } else {
      return triangular (n - 1) + n;
   }
}


triangular(1);	// 1
triangular(2);	// 3
triangular(3);	// 6
triangular(4);	// 10
```

