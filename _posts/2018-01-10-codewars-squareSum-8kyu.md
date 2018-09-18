---
layout: post
title: "squareSum.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 배열(array) 알고리즘 문제

<br>

## problem

squareSum / square_sum / SquareSum method

so that it squares each number passed into it

and then sums the results together.

<br>

## solution 01

```javascript
// a: sum
// b: number

function squareSum(array) {
   return array.reduce((a, b) => a + (b * b), 0);
}


squareSum([2, 2]);	// 8
squareSum([3, 3]);	// 18
```

<br>

## solution 02

```javascript
function squareSum(array) {
   return array.reduce(function(sum, number) {
      return (number * number) + sum;
   }, 0)
}


squareSum([2, 2]);	// 8
squareSum([3, 3]);	// 18
```

<br>

## solution 03

```javascript
function squareSum(array) {
   let result = 0;
   
   array.forEach(function(number) {
      result += number * number;
   });
   return result;
}


squareSum([2, 2]);	// 8
squareSum([3, 3]);	// 18
```

