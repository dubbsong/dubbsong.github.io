---
layout: post
title: "factorial.js"
categories: dev
tags: algo
---

#### 계승(factorial) + 반복문(for loop) 알고리즘 문제

<br>

## problem

Factorial of n:

The factorial of n is

the product of all the integers preceding n,

starting with 1.

<br>

> 1! = 1
>
> 2! = 1 x 2 = 2
>
> 3! = 1 x 2 x 3 = 6
>
> 4! = 1 x 2 x 3 x 4 = 24
>
> 5! = 1 x 2 x 3 x 4 x 5 = 120

<br>

## solution 01

```javascript
function factorial(n) {
   let result = 1;
   
   for (let i = 1; i <= n; i++) {
      result *= i;
   }
   return result;
}


factorial(3);	// 6
factorial(4);	// 24
factorial(5);	// 120
```

<br>

## solution 02

```javascript
function factorial(n) {
   let result = 1;
   
   for (let i = n; i > 0; i--) {
      result *= i;
   }
   return result;
}


factorial(3);	// 6
factorial(4);	// 24
factorial(5);	// 120
```

