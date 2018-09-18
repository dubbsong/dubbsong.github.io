---
layout: post
title: "toBinary.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Given a non-negative integer '`number`',

write a function '`toBinary`'

which returns that number in a binary format.

<br>

## solution 01

```javascript
function toBinary(number) {
   return parseInt(number.toString(2));
}


toBinary(0);	// 0
toBinary(1);	// 1
toBinary(2);	// 10
toBinary(3);	// 11
toBinary(4);	// 100
toBinary(5);	// 101
toBinary(6);	// 110
toBinary(7);	// 111
toBinary(8);	// 1000
toBinary(9);	// 1001
toBinary(10);	// 1010
```

> `parseInt()` 메소드
>
> 문자열을 파싱(해석)해서 정수(integer)를 반환한다.

<br>

## solution 02

```javascript
function toBinary(number) {
   return +number.toString(2);
}


toBinary(0);	// 0
toBinary(1);	// 1
toBinary(2);	// 10
toBinary(3);	// 11
toBinary(4);	// 100
toBinary(5);	// 101
toBinary(6);	// 110
toBinary(7);	// 111
toBinary(8);	// 1000
toBinary(9);	// 1001
toBinary(10);	// 1010
```

<br>

## solution 03

```javascript
function toBinary(number) {
   return Number(number).toString(2);
}


toBinary(0);	// 0
toBinary(1);	// 1
toBinary(2);	// 10
toBinary(3);	// 11
toBinary(4);	// 100
toBinary(5);	// 101
toBinary(6);	// 110
toBinary(7);	// 111
toBinary(8);	// 1000
toBinary(9);	// 1001
toBinary(10);	// 1010
```

