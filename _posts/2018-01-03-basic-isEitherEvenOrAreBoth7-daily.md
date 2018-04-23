---
layout: post
title: "isEitherEvenOrAreBoth7.js"
categories: dev
tags: algo
---

#### 숫자(number) + 논리 연산자(Logical Operators) 활용 알고리즘 문제

<br>

## problem

Write a function called '`isEitherEvenOrAreBoth7`'.

<br>

Given two numbers,

'isEitherEvenOrAreBoth7' returns

whether at least one of them is even,

or both of them are 7.

<br>

## solution 01

```javascript
function isEitherEvenOrAreBoth7(num1, num2) {
   return (num1 === 7 && num2 === 7) || (num1 % 2 === 0 || num2 % 2 === 0);
}


isEitherEvenOrAreBoth7(2, 3);	// true
isEitherEvenOrAreBoth7(3, 7);	// false
```

> `논리 연산자 (Logical Operators)`
>
> `&&`: and
>
> `||`: or
>
> `!`: not
>
> 논리 연산자는 Boolean 값과 함께 사용하여 Boolean 값을 반환하는 것이 일반적이다.
>
> 논리 연산자는 피연산자 중 하나를 반환한다.

<br>

## solution 02

```javascript
function isEitherEvenOrAreBoth7(num1, num2) {
   return (num1 === 7 && num2 === 7) || !(num1 % 2 && num2 % 2);
}


isEitherEvenOrAreBoth7(2, 3);	// true
isEitherEvenOrAreBoth7(3, 7);	// false
```



