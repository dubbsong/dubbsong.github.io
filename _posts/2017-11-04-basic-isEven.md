---
layout: post
title: "isEven.js"
categories: dev
tags: algo
---

#### 조건문(if) + 불린(boolean) 알고리즘 문제

<br>

## problem

Write a function called '`isEven`'.

Given an integer,

'isEven' returns whether the integer is even or not.

<br>

> \* even: true
>
> \* odd: false

<br>

## solution 01

```javascript
function isEven(num) {
   if (num % 2 === 0) {
      return true;
   } else {
      return false;
   }
}


isEven(42);	// true
isEven(19);	// false
```

> `조건문 (if/else)`
>
> `if` (조건식) `{` return true; `}`
>
> `else` `{` return false; `}`

<br>

## solution 02

```javascript
function isEven(num) {
   return num % 2 === 0 ? true: false;
}


isEven(42);	// true
isEven(19);	// false
```

> `삼항 연산자 (ternary operator)`
>
> 조건식 `?` 조건이 true일 때 반환하는 값 `:` 조건이 false일 때 반환하는 값

<br>

## solution 03

```javascript
const isEven = num => num % 2 === 0 ? true : false;


isEven(42);	// true
isEven(19);	// false
```

> `Arrow function`(`=>`)은 [함수 표현식](https://dubbsong.github.io/javascript/2017/11/14/js-function-expression/)을 사용한다.
>
> `const` 변수명 `=` 매개변수 `=>` 조건식 `?` true `:` false

<br>