---
layout: post
title: "modulo.js"
categories: dev
tags: algo
---

#### 반복문(while loop) 알고리즘 문제

<br>

## problem

The modulo operator(%) computes the remainder

after dividing its left operand by its right one.

<br>

> 5 % 2		// 1
>
> 8 % 10		// 8
>
> 7 % 5		// 2

<br>

Write a function called '`modulo`'

that works like the `%` operator,

but without using it.

<br>

## solution 01

```javascript
function modulo(num, num2) {
   while (num > num2) {
      num = num - num2;
   }
   return num;
}


modulo(5, 2);	// 1
modulo(8, 10);	// 8
modulo(7, 5);	// 2
```

<br>

## solution 02

```javascript
function modulo(num, num2) {
   return num - parseInt(num/num2) * num2;
}


modulo(5, 2);	// 1
modulo(8, 10);	// 8
modulo(7, 5);	// 2
```

