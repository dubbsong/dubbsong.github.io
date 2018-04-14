---
layout: post
title: "isOldEnoughToDrink.js"
categories: dev
tags: algo
---

#### 조건문(if) + 불린(boolean) 알고리즘 문제

<br>

## problem

Write a function called '`isOldEnoughToDrink`'.

Given a number, in this case an age,

'isOldEnoughToDrink' returns whether a person

of this given age is old enough to legally drink

in the United States.

<br>

\* <u>The legal drinking age in the United States is 21.</u>

<br>

## solution 01

```javascript
function isOldEnoughToDrink(age) {
   if (age >= 21) {
      return true;
   } else {
      return false;
   }
}


isOldEnoughToDrink(21);		// true
isOldEnoughToDrink(20);		// false
```

<br>

## solution 02

```javascript
function isOldEnoughToDrink(age) {
   return age >= 21 ? true : false;
}


isOldEnoughToDrink(21);		// true
isOldEnoughToDrink(20);		// false
```

> `삼항 연산자 (ternary operator)`
>
> 조건식 `?` 조건이 true일 때 반환하는 값 `:` 조건이 false일 때 반환하는 값

<br>

## solution 03

```javascript
const isOldEnoughToDrink = age => age >= 21 ? true : false;


isOldEnoughToDrink(21);		// true
isOldEnoughToDrink(20);		// false
```

> `Arrow function`(`=>`)은 [익명 함수](https://dubbsong.github.io/javascript/2017/11/14/js-function-expression/)로만 사용할 수 있다.
>
> 따라서 `=>`을 호출하기 위해서는 [함수 표현식](https://dubbsong.github.io/javascript/2017/11/14/js-function-expression/)을 사용한다.

<br>