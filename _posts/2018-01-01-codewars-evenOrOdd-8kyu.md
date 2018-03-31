---
layout: post
title: "evenOrOdd.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 불린(boolean) 알고리즘 문제

<br>

## problem

Create a function

that takes an integer as an argument

and returns "Even" for even numbers

or "Odd" for odd numbers.

<br>

## solution 01

```javascript
function evenOrOdd(n) {
   if (n % 2 === 0) {
      return 'Even';
   } else {
      return 'Odd';
   }
}


evenOrOdd(2);	// Even
evenOrOdd(1);	// Odd
```

<br>

## solution 02

```javascript
function evenOrOdd(n) {
   return n % 2 === 0 ? 'Even' : 'Odd';
}


evenOrOdd(2);	// Even
evenOrOdd(1);	// Odd
```

<br>

## solution 03

```javascript
function evenOrOdd(n) {
   return n % 2 ? 'Odd' : 'Even';
}


evenOrOdd(2);	// Even
evenOrOdd(1);	// Odd
```

<br>

## solution 04

```javascript
const evenOrOdd = n => n % 2 ? 'Odd' : 'Even';


evenOrOdd(2);	// Even
evenOrOdd(1);	// Odd
```

