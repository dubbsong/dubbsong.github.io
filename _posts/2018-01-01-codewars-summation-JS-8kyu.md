---
layout: post
title: "summation.js (8kyu)"
categories: codewars
tags: Algorithm
---

#### 반복문(for loop) + 기본 수학(basic math) 활용 알고리즘 문제

<br>

## problem

Write a program

that finds the `summation` of every number

between `1` and `n`.

<br>

The number will always be a positive integer greater than 0.

<br>

## solution 01

```javascript
function summation(n) {
   let result = 0;
   
   for (let i = 0; i <= n; i++) {
      result += i;
   }
   return result;
}


console.log(summation(10));	// 55
console.log(summation(100));	// 5050
```

<br>

## solution 02

```javascript
function summation(n) {
   return n * (n + 1) / 2;
}


console.log(summation(10));	// 55
console.log(summation(100));	// 5050
```

<br>

## solution 03

```javascript
const summation = n => n * (n + 1) / 2;


console.log(summation(10));	// 55
console.log(summation(100));	// 5050
```

<br>