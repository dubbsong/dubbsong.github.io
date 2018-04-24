---
layout: post
title: "assertEqual.js"
categories: dev
tags: algo
---

#### 불린(boolean) 활용 알고리즘 문제

<br>

## problem

Write an '`assertEqual`' function from scratch.

<br>

It should compare `actual` and `expected` values

with strict equality (not typecasting).

<br>

```javascript
// SUCCESS CASE

function multiplyByTwo(n) {
   return n * 2;
}


multiplyByTwo(2);	// returns 4
assertEqual(output, 4, 'it doubles 2 to 4');	// passed
```

<br>

```javascript
// FAILURE CASE

function multiplyByTwo(n) {
   return (n * 2) + 1;	// an incorrect implementation
}


multiplyByTwo(2);	// returns 5
assertEqual(output, 4, 'it doubles 2 to 4');
// FAILED [it doubles 2 to 4] expected "4", but got "5"
```

<br>

## solution

```javascript
function assertEqual(actual, expected, testName) {
   return actual === expected
   	? 'passed'
   	: `FAILED [${testName}] Expected "${expected}", but got "${actual}"`;
}


assertEqual(4, 4, 'it doubles 2 to 4');	// passed
assertEqual(2, 4, 'it doubles 2 to 4');	// FAILED [it doubles 2 to 4] Expected "4", but got "2"
```

> `삼항 연산자 (ternary operator)`
>
> 조건식 `?` 조건이 true일 때 반환하는 값 `:` 조건이 false일 때 반환하는 값

<br>