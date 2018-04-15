---
layout: post
title: "areSameLength.js"
categories: dev
tags: algo
---

#### 조건문(if) + 불린(boolean) 알고리즘 문제

<br>

## problem

Write a function called '`areSameLength`'.

Given two strings,

'areSameLength' returns true

if they are of the same length,

and false otherwise.

<br>

## solution 01

```javascript
function areSameLength(string1, string2) {
   if (string1.length === string2.length) {
      return true;
   } else {
      return false;
   }
}


areSameLength('Sam', 'Leo');		// true
areSameLength('Wassup', 'bro?');	// false
```

> `조건문 (if/else)`
>
> `if` (조건식) `{` return true; `}`
>
> `else` `{` return false; `}`

<br>

## solution 02

```javascript
function areSameLength(string1, string2) {
   return string1.length === string2.length ? true : false;
}


areSameLength('Sam', 'Leo');		// true
areSameLength('Wassup', 'bro?');	// false
```

> `삼항 연산자 (ternary operator)`
>
> 조건식 `?` 조건이 true일 때 반환하는 값 `:` 조건이 false일 때 반환하는 값

<br>

## solution 03

```javascript
const areSameLength = (string1, string2) => string1.length === string2.length ? true : false;


areSameLength('Sam', 'Leo');		// true
areSameLength('Wassup', 'bro?');	// false
```

> `Arrow function`(`=>`)은 [함수 표현식](https://dubbsong.github.io/javascript/2017/11/14/js-function-expression/)을 사용한다.
>
> `const` 변수명 `=` (매개변수1, 매개변수2) `=>` 조건식 `?` true `:` false

<br>