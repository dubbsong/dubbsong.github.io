---
layout: post
title: "assertArraysEqual.js"
categories: dev
tags: algo
---

#### 조건문(if) + 반복문(for loop) 활용 알고리즘 문제

<br>

## problem

Write an '`assertArraysEqual`' function from scratch.

<br>

Assume that the arrays

in question contain only scalar values.

(i.e., simple values like strings or numbers)

<br>

Do not use JSON.stringify(), Array.join(), or any other

"convert the array to a string so I can compare two strings"

type of technique to implement this.

<br>

```javascript
// SUCCESS CASE

var expected = ['s', 's', 'u', 'p'];
var actual = 'ssup'.split('');
assertArraysEqual(actual, expected, 'splits string into array of characters');	// passed
```

<br>

```javascript
// FAILURE CASE

var expected = [1, 1, 2, 3];
var actual = 'fibo'.split('');
assertArraysEqual(actual, expected, 'generates first 4 Fibonacci numbers');
// FAILED [generates first 4 Fibonacci numbers] Expected "1, 1, 2, 3", but got "f, i, b, o"
```

<br>

## solution

```javascript
function assertArraysEqual(actual, expected, testName) {
   let isSame = true;
   
   if (actual.length !== expected.length) {
      isSame = false;
   } else {
      for (let i = 0; i < actual.length; i++) {
         if (actual[i] !== expected[i]) {
            isSame = false;
         }
      }
   }
   return isSame
   	? 'passed'
   	: `FAILED [${testName}] Expected "${expected}", but got "${actual}"`;
}


assertArraysEqual('ssup'.split(''), ['s', 's', 'u', 'p'], 'splits string into array of characters');	// passed
assertArraysEqual('fibo'.split(''), [1, 1, 2, 3], 'generates first 4 Fibonacci numbers');
// FAILED [generates first 4 Fibonacci numbers] Expected "1, 1, 2, 3", but got "f, i, b, o"
```

> `삼항 연산자 (ternary operator)`
>
> 조건식 `?` 조건이 true일 때 반환하는 값 `:` 조건이 false일 때 반환하는 값

<br>