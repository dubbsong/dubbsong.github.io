---
layout: post
title: "howManyDays.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(switch) 알고리즘 문제

<br>

## problem

Complete function '`howManyDays`',

function accept 1 parameter 'month',

means the month of year,

different month has different days,

return a number that how many days in this month.

<br>

## solution 01

```javascript
function howManyDays(month) {
   switch (month) {
      case 2: return 28
      case 4:
      case 6:
      case 9:
      case 11: return 30
   }
   return 31
}


howManyDays(1);	// 31
howManyDays(2);	// 28
howManyDays(11);	// 30
howManyDays(12);	// 31
```

<br>

## solution 02

```javascript
function howManyDays(month) {
   switch (month) {
      case 4:
      case 6:
      case 9:
      case 11:
         return 30
      case 2:
         return 28
      default:
         return 31
   }
}


howManyDays(1);	// 31
howManyDays(2);	// 28
howManyDays(11);	// 30
howManyDays(12);	// 31
```

<br>

## solution 03

```javascript
function howManyDays(month) {
   switch (month) {
      case 2: return 28
      case 4: case 6: case 9: case 11: return 30
      default: return 31
   }
}


howManyDays(1);	// 31
howManyDays(2);	// 28
howManyDays(11);	// 30
howManyDays(12);	// 31
```

<br>

## solution 04

```javascript
function howManyDays(month) {
   return new Date(2018, month, 0).getDate();
}


howManyDays(1);	// 31
howManyDays(2);	// 28
howManyDays(11);	// 30
howManyDays(12);	// 31
```

