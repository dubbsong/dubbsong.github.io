---
layout: post
title: "getLargerString.js"
categories: dev
tags: algo
---

#### 조건문(if) + 불린(boolean) 알고리즘 문제

<br>

## problem

Write a function called '`getLargerString`'.

Given two strings,

'getLargerString' return the longer string.

<br>

\* <u>If the strings are the same length, return string1.</u>

<br>

## solution 01

```javascript
function getLargerString(string1, string2) {
   if (string1.length >= string2.length) {
      return string1;
   } else {
      return string2;
   }
}


getLargerString('Wassup', 'bro?');	// Wassup
getLargerString('Leo', 'Sam');		// Leo
```

> `조건문 (if/else)`
>
> `if` (조건식) `{` return true; `}`
>
> `else` `{` return false; `}`

<br>

## solution 02

```javascript
function getLargerString(string1, string2) {
   return string1.length >= string2.length ? string1 : string2;
}


getLargerString('Wassup', 'bro?');	// Wassup
getLargerString('Leo', 'Sam');		// Leo
```

> `삼항 연산자 (ternary operator)`
>
> 조건식 `?` 조건이 true일 때 반환하는 값 `:` 조건이 false일 때 반환하는 값

<br>

## solution 03

```javascript
const getLargerString = (string1, string2) => string1.length >= string2.length ? string1 : string2;


getLargerString('Wassup', 'bro?');	// Wassup
getLargerString('Leo', 'Sam');		// Leo
```

> `Arrow function`(`=>`)은 [함수 표현식](https://dubbsong.github.io/javascript/2017/11/14/js-function-expression/)을 사용한다.
>
> `const` 변수명 `=` 매개변수 `=>` 조건식 `?` true `:` false

<br>