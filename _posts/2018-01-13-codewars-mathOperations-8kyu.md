---
layout: post
title: "mathOperations.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if/switch) 알고리즘 문제

<br>

## problem

Your task is to create a function

that does four basic mathematical operations.

<br>

The function should take three arguments:

operation(string/char), value1(number), value2(number).

<br>

The function should return result of numbers

after applying the chosen operation.

<br>

## solution 01

```javascript
function mathOperations(operation, value1, value2) {
   if (operation === '+') {
      return value1 + value2;
   } else if (operation === '-') {
      return value1 - value2;
   } else if (operation === '*') {
      return value1 * value2;
   } else if (operation === '/') {
      return value1 / value2;
   } else {
      return 0;
   }
}


mathOperations('+', 4, 2);	// 6
mathOperations('-', 4, 2);	// 2
mathOperations('*', 4, 2);	// 8
mathOperations('/', 4, 2);	// 6
```

<br>

## solution 02

```javascript
function mathOperations(operation, value1, value2) {
   switch (operation) {
      case '+': return value1 + value2;
      case '-': return value1 - value2;
      case '*': return value1 * value2;
      case '/': return value1 / value2;
      default: return 0;
   }
}


mathOperations('+', 4, 2);	// 6
mathOperations('-', 4, 2);	// 2
mathOperations('*', 4, 2);	// 8
mathOperations('/', 4, 2);	// 6
```

<br>

## solution 03

```javascript
function mathOperations(operation, value1, value2) {
   const cases = {
      '+': value1 + value2,
      '-': value1 - value2,
      '*': value1 * value2,
      '/': value1 / value2
   }
   return cases[operation];
}


mathOperations('+', 4, 2);	// 6
mathOperations('-', 4, 2);	// 2
mathOperations('*', 4, 2);	// 8
mathOperations('/', 4, 2);	// 6
```

