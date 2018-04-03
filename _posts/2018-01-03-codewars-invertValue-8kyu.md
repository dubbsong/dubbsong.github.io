---
layout: post
title: "invertValue.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) 알고리즘 문제

<br>

## problem

Given a set of numbers,

return the additive inverse of each.

<br>

Each positive becomes negatives,

and the negatives become positives.

<br>

## solution 01

```javascript
function invertValue(array) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      if (array[i] > 0) {
         result.push(-array[i]);
      } else if (array[i] < 0) {
         result.push(array[i] * -1);
      } else {
         result.push(0);
      }
   }
   return result;
}


invertValue([0]);		 // 0
invertValue([1, 2, 3, 4]);	// [-1, -2, -3, -4]
invertValue([-1, -2, -3, -4]);	// [1, 2, 3, 4]
```

<br>

## solution 02

```javascript
function invertValue(array) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      if (array[i] === 0) {
         result.push(0);
      } else {
         result.push(-array[i]);
      }
   }
   return result;
}


invertValue([0]);		 // 0
invertValue([1, 2, 3, 4]);	// [-1, -2, -3, -4]
invertValue([-1, -2, -3, -4]);	// [1, 2, 3, 4]
```

<br>

## solution 03

```javascript
function invertValue(array) {
   return array.map(a => a === 0 ? a : -a);
}


invertValue([0]);		 // 0
invertValue([1, 2, 3, 4]);	// [-1, -2, -3, -4]
invertValue([-1, -2, -3, -4]);	// [1, 2, 3, 4]
```

