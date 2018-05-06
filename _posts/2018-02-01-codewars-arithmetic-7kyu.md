---
layout: post
title: "arithmetic.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if / switch) 활용 알고리즘 문제

<br>

## problem

Given two numbers and an arithmetic operator,

return the result of the two numbers

having that operator used on them.

<br>

'`a`' and '`b`' will both be positive integers,

and '`a`' will always be the first number in the operation,

and '`b`' always the second.

<br>

The four operators are

'`add`', '`subtract`', '`multiply`', '`divide`'.

<br>

## solution 01

```javascript
function arithmetic(a, b, operator) {
   if (operator === 'add') {
      return a + b;
   } else if (operator === 'subtract') {
      return a - b;
   } else if (operator === 'multiply') {
      return a * b;
   } else {
      return a / b;
   }
}


arithmetic(4, 2, 'add');	// 6
arithmetic(4, 2, 'subtract');	// 2
arithmetic(4, 2, 'multiply');	// 8
arithmetic(4, 2, 'divide');	// 2
```

<br>

## solution 02

```javascript
function arithmetic(a, b, operator) {
   switch(operator) {
      case 'add': return a + b;
      case 'subtract': return a - b;
      case 'multiply': return a * b;
      case 'divide': return a / b;
   }
}


arithmetic(4, 2, 'add');	// 6
arithmetic(4, 2, 'subtract');	// 2
arithmetic(4, 2, 'multiply');	// 8
arithmetic(4, 2, 'divide');	// 2
```

<br>

## solution 03

```javascript
const arithmetic = (a, b, operator) => ({
   'add': a + b,
   'subtract': a - b,
   'multiply': a * b,
   'divide': a / b
}[operator]);


arithmetic(4, 2, 'add');	// 6
arithmetic(4, 2, 'subtract');	// 2
arithmetic(4, 2, 'multiply');	// 8
arithmetic(4, 2, 'divide');	// 2
```

