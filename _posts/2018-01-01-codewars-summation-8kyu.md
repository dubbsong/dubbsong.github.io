---
layout: post
title: "summation.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) 알고리즘 문제

<br>

## problem

Write a program

that finds the '`summation`' of every number

between 1 and num.

<br>

The number will always be a positive integer

greater than 0.

<br>

## solution 01

```javascript
function summation(num) {
   let result = 0;
   
   for (let i = 0; i <= num; i++) {
      result += i;
   }
   return result;
}


summation(10);	// 55
summation(100);	// 5050
```

<br>

## solution 02

```javascript
const summation = num => num * (num + 1) / 2;


summation(10);	// 55
summation(100);	// 5050
```

