---
layout: post
title: "century.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 불린(boolean) + 반복문(for loop) + 메소드 활용 알고리즘 문제

<br>

## problem

Given a year, return the century it is in.

<br>

The first century spans from the year 1 up to

and including the year 100,

the second century spans from the year 101 up to

and including the year 200, etc

<br>

## solution 01

```javascript
function century(year) {
   let result = 0;
   
   for (let i = 0; i < year; i++) {
      if (i % 100 === 0) {
         result += 1;
      }
   }
   return result;
}


century(10);	// 1
century(100);	// 1
century(101);	// 2
century(1988);	// 20
century(2018);	// 21
```

<br>

## solution 02

```javascript
function century(year) {
   if (year % 100 === 0) {
      return parseInt(year / 100);
   } else {
      return parseInt(year / 100) + 1;
   }
}


century(10);	// 1
century(100);	// 1
century(101);	// 2
century(1988);	// 20
century(2018);	// 21
```

<br>

## solution 03

```javascript
const century = year => year % 100 === 0 ? parseInt(year / 100) : parseInt(year / 100) + 1;


century(10);	// 1
century(100);	// 1
century(101);	// 2
century(1988);	// 20
century(2018);	// 21
```

