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

> `반복문 (while loop)`
>
> 조건문이 참이면 코드를 계속해서 반복 실행한다.
>
> 조건문이 거짓이 되면 실행을 종료하고 반복문을 빠져나간다.
>
> 조건문이 언제나 참이면 `무한 루프`가 된다.
>
> `while` (조건문) `{` 구문; `}`

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

> `parseInt()` 메소드
>
> 문자열을 정수로 반환한다.