---
layout: post
title: "generateRange.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop / while loop) + 메소드 활용 알고리즘 문제

<br>

## problem

Implement a function named '`generateRange`',

which takes three arguments

and generates a range of integers

from '`min`' to '`max`', with the '`step`'.

<br>

The first integer is the minimum value,

the second is the maximum of the range

and the third is the step.

<br>

## solution 01

```javascript
function generateRange(min, max, step) {
   let result = [];
   
   for (let i = min; i <= max; i += step) {
      result.push(i);
   }
   return result;
}


generateRange(2, 10, 2);	// [2, 4, 6, 8, 10]
generateRange(2, 10, 2);	// [1, 4, 7, 10]
```

<br>

## solution 02

```javascript
function generateRange(min, max, step) {
   let result = [];
   
   while (min <= max) {
      result.push(min);
      min += step;
   }
   return result;
}


generateRange(2, 10, 2);	// [2, 4, 6, 8, 10]
generateRange(2, 10, 2);	// [1, 4, 7, 10]
```

<br>

## solution 03

```javascript
function generateRange(min, max, step) {
   return min > max ? [] : [min, ...generateRange(min + step, max, step)];
}


generateRange(2, 10, 2);	// [2, 4, 6, 8, 10]
generateRange(2, 10, 2);	// [1, 4, 7, 10]
```

