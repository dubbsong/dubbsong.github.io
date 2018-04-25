---
layout: post
title: "isPasswordLongEnough.js"
categories: dev
tags: algo
---

#### 조건문(if) + 불린(boolean) 알고리즘 문제

<br>

Write a function called '`isPasswordLongEnough`'.

Given a string and a integer,

in this case a password and a minimum required length,

'isPasswordLongEnough' return

whether the inputted password is long enough.

<br>

## solution 01

```javascript
function isPasswordLongEnough(password, minimumLength) {
   if (password.length >= minimumLength) {
      return true;
   } else {
      return false;
   }
}


isPasswordLongEnough('qlqjs12', 8); 	// false
isPasswordLongEnough('votmdnjem', 8);	// true
```

> `조건문 (if/else)`
>
> `if` (조건식) `{` return true; `}`
>
> `else` `{` return false; `}`

<br>

## solution 02

```javascript
function isPasswordLongEnough(password, minimumLength) {
   return password.length >= minimumLength ? true : false;
}


isPasswordLongEnough('qlqjs12', 8); 	// false
isPasswordLongEnough('votmdnjem', 8);	// true
```

> `삼항 연산자 (ternary operator)`
>
> 조건식 `?` 조건이 true일 때 반환하는 값 `:` 조건이 false일 때 반환하는 값

<br>

## solution 03

```javascript
const isPasswordLongEnough = (password, minimumLength) => password.length >= minimumLength ? true : false;


isPasswordLongEnough('qlqjs12', 8); 	// false
isPasswordLongEnough('votmdnjem', 8);	// true
```

> `Arrow function`(`=>`)은 [함수 표현식](https://dubbsong.github.io/javascript/2017/11/14/js-function-expression/)을 사용한다.
>
> `const` 변수명 `=` (매개변수1, 매개변수2) `=>` 조건식 `?` true `:` false

<br>