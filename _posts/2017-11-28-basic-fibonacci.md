---
layout: post
title: "fibonacci.js"
categories: dev
tags: algo
---

#### 피보나치 수(fibonacci) + 반복문(for loop) 알고리즘 문제

<br>

## problem

Compute the nth Fibonacci Number:

The fibonacci numbers are represented

by the following sequence:

<br>

> 1, 1, 2, 3, 5, 8, 13, 21, 34, 55...

<br>

Notice that each fibonacci number can be computed

by adding the previous two fibonacci numbers,

with the exception of the first two:

fibonacci(0) and fibonacci(1).

<br>

>fibonacci(0) is 1
>
>fibonacci(1) is 1
>
>fibonacci(n) is fibonacci(n - 1) + fibonacci(n - 2)

<br>

Write a function called '`fibonacci`'

that accepts a number n as a parameter

and computes the nth fibonacci number

using the above rules.

<br>

## solution 01

```javascript
function fibonacci(n) {
   let arr = [1, 1];
   
   for (let i = 2; i <= n; i++) {
      arr.push(arr[i - 1] + arr[i - 2]);
   }
   return arr[n];
}


fibonacci(0);	// 1
fibonacci(8);	// 34
fibonacci(13);	// 377
```

<br>

## solution 02

```javascript
function fibonacci(n) {
   let sum = 1;
   let pre = 0;
   let next;
   
   for (let i = 0; i < n; i++) {
      next = sum;
      sum += pre;
      pre = next;
   }
   return sum;
}


fibonacci(0);	// 1
fibonacci(8);	// 34
fibonacci(13);	// 377
```

