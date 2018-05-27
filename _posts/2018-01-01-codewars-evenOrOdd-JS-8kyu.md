---
layout: post
title: "evenOrOdd.js (8kyu)"
categories: codewars
tags: Algorithm
---

#### 조건문(if) 활용 알고리즘 문제

<br>

## problem

Create a function

that takes an integer as an argument

and returns '`Even`' for even numbers

or '`Odd`' for odd numbers.

<br>

## solution 01

```javascript
function evenOrOdd(number) {
   if (number % 2 === 0) {
      return 'Even';
   } else {
      return 'Odd';
   }
}


evenOrOdd(1);	// Odd
evenOrOdd(2);	// Even
```

<br>

## solution 02

```javascript
function evenOrOdd(number) {
   if (number % 2) {
      return 'Odd';
   } else {
      return 'Even';
   }
}


evenOrOdd(1);	// Odd
evenOrOdd(2);	// Even
```

<br>

## solution 03

```javascript
function evenOrOdd(number) {
   return number % 2 === 0 ? 'Even' : 'Odd';
}


evenOrOdd(1);	// Odd
evenOrOdd(2);	// Even
```

> 삼항 연산자 (Ternary operator)
>
> 조건식 `?` 조건이 true일 때 반환하는 값 `:` 조건이 false일 때 반환하는 값

<br>

## solution 04

```javascript
function evenOrOdd(number) {
   return number % 2 ? 'Odd' : 'Even';
}


evenOrOdd(1);	// Odd
evenOrOdd(2);	// Even
```

<br>

## solution 05

```javascript
const evenOrOdd = number => number % 2 ? 'Odd' : 'Even';


evenOrOdd(1);	// Odd
evenOrOdd(2);	// Even
```

<br>