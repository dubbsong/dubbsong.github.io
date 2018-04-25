---
layout: post
title: "getMax.js"
categories: dev
tags: algo
---

#### 조건문(if) + 불린(boolean) 알고리즘 문제

<br>

## problem

Write a function called '`getMax`'.

Given two numbers,

'getMax' returns the larger of these two numbers.

<br>

\* <u>If the two numbers are equal, return either one.</u>

<br>

## solution 01

```javascript
function getMax(num1, num2) {
   if (num1 > num2) {
      return num1;
   } else {
      return num2;
   }
}


getMax(19, 34);		// 34
getMax(2.3, -19);	// 2.3
```

> `조건문 (if/else)`
>
> `if` (조건식) `{` return true; `}`
>
> `else` `{` return false; `}`

<br>

## solution 02

```javascript
function getMax(num1, num2) {
   return num1 > num2 ? num1 : num2;
}


getMax(19, 34);		// 34
getMax(2.3, -19);	// 2.3
```

> `삼항 연산자 (ternary operator)`
>
> 조건식 `?` 조건이 true일 때 반환하는 값 `:` 조건이 false일 때 반환하는 값

<br>

## solution 03

```javascript
function getMax(num1, num2) {
   return Math.max(num1, num2);
}


getMax(19, 34);		// 34
getMax(2.3, -19);	// 2.3
```

> `Math.max()` 메소드
>
> 입력된 숫자 중 가장 큰 숫자를 반환한다.

<br>

## solution 04

```javascript
const getMax = (num1, num2) => num1 > num2 ? num1 : num2;


getMax(19, 34);		// 34
getMax(2.3, -19);	// 2.3
```

> `Arrow function`(`=>`)은 [함수 표현식](https://dubbsong.github.io/javascript/2017/11/14/js-function-expression/)을 사용한다.
>
> `const` 변수명 `=` (매개변수1, 매개변수2) `=>` 조건식 `?` true `:` false

<br>