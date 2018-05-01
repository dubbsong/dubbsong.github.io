---
layout: post
title: "getSum.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop / while) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Given two integers '`a`' and '`b`'.

which can be positive or negative,

find the sum of all the numbers

between including them too and return it.

<br>

If the two numbers are equal return 'a' or 'b'.

<br>

## solution 01

```javascript
function getSum(a, b) {
   const max = Math.max(a, b);
   const min = Math.min(a, b);
   let result = 0;
   
   for (let i = min; i <= max; i++) {
      result += i;
   }
   return result;
}


getSum(1, 4);	// 10
getSum(-1, 4);	// 9
getSum(-4, -2);	// -9
```

<br>

## solution 02

```javascript
function getSum(a, b) {
   const max = a > b ? a : b;
   const min = a > b ? b : a;
   let result = 0;
   
   for (let i = min; i <= max; i++) {
      result += i;
   }
   return result;
}


getSum(1, 4);	// 10
getSum(-1, 4);	// 9
getSum(-4, -2);	// -9
```

<br>

## solution 03

```javascript
function getSum(a, b) {
   const max = Math.max(a, b);
   const min = Math.min(a, b);
   return (max - min + 1) * (max + min) / 2;
}


getSum(1, 4);	// 10
getSum(-1, 4);	// 9
getSum(-4, -2);	// -9
```

<br>

## solution 04

```javascript
function getSum(a, b) {
   let result = 0;
   
   if (a < b) {
      while (a <= b) {
         result += a++;
      }
   } else {
      while (a >= b) {
         result += a--;
      }
   }
   return result;
}


getSum(1, 4);	// 10
getSum(-1, 4);	// 9
getSum(-4, -2);	// -9
```

