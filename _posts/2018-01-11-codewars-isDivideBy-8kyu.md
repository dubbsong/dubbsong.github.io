---
layout: post
title: "isDivideBy (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 불린(boolean) 알고리즘 문제

<br>

## problem

Your task is to create function '`isDivideBy`'

to check if an integer number is divisible

by each out of two arguments.

<br>

## solution 01

```javascript
function idDivideBy(number, a, b) {
   if (number % a === 0 && number % b === 0) {
      return true;
   } else {
      return false;
   }
}


isDivideBy(8, 2, 4);	// true
isDivideBy(45, 3, 9);	// true
isDivideBy(45, 2, 8);	// false
```

<br>

## solution 02

```javascript
const isDivideBy = (number, a, b) => number % a === 0 && number % b === 0;


isDivideBy(8, 2, 4);	// true
isDivideBy(45, 3, 9);	// true
isDivideBy(45, 2, 8);	// false
```

<br>

## solution 03

```javascript
const isDivideBy = (number, a, b) => !(number % a || number % b);


isDivideBy(8, 2, 4);	// true
isDivideBy(45, 3, 9);	// true
isDivideBy(45, 2, 8);	// false
```

