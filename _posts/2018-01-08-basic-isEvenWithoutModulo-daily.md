---
layout: post
title: "isEvenWithoutModulo.js"
categories: dev
tags: algo
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function called '`isEvenWithoutModulo`'.

<br>

Given a number,

'isEvenWithoutModulo' returns whether it is even.

<br>

> Notes:
>
> It does so without using the modulo operator(%).
>
> It should work for negative numbers and zero.

<br>

## solution

```javascript
function isEvenWithoutModulo(num) {
   return num / 2 === Math.floor(num / 2);
}


isEvenWithoutModulo(2);	// true
isEvenWithoutModulo(1);	// false
isEvenWithoutModulo(-1);	// false
isEvenWithoutModulo(0);	// true
```

> `Math.floor()` 메소드
>
> 주어진 숫자와 같거나 작은 정수 중에서 가장 큰 수를 반환한다.

<br>