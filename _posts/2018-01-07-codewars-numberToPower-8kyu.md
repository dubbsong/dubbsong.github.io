---
layout: post
title: "numberToPower.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) 알고리즘 문제

<br>

## problem

The goal is to create a function '`numberToPower`'

that '`raises`' the number up to power.

<br>

## solution 01

```javascript
function numberToPower(number, power) {
   let result = 1;
   
   for (let i = 1; i <= power; i++) {
      result *= number;
   }
   return result;
}


numberToPower(4, 2);	// 16
numberToPower(10, 0);	// 1
numberToPower(10, 4);	// 10000
```

<br>

## solution 02

```javascript
const numberToPower = (number, power) => power > 0 ? number * numberToPower(number, power - 1) : 1;


numberToPower(4, 2);	// 16
numberToPower(10, 0);	// 1
numberToPower(10, 4);	// 10000
```

