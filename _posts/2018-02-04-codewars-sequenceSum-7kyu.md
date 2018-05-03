---
layout: post
title: "sequenceSum.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) 알고리즘 문제

<br>

## problem

Your task is to make function,

which returns the sum of a sequence of integers.

<br>

The sequence is defined by 3 non-negative value:

`begin`, `end`, `step`.

<br>

If begin value is greater than the end,

function should returns 0.

<br>

## solution 01

```javascript
function sequenceSum(begin, end, step) {
   let result = 0;
   
   for (let i = begin; i <= end; i+=step) {
      result += i;
   }
   return result;
}


sequenceSum(1, 5, 1);	// 15 (1 + 2 + 3 + 4 + 5)
sequenceSum(2, 6, 2);	// 12 (2 + 4 + 6)
sequenceSum(1, 5, 3);	// 5 (1 + 4)
```

<br>

## solution 02

```javascript
function sequenceSum(begin, end, step) {
   let result = 0;
   
   if (begin > end) return 0
   if (begin === end) return end
   
   for (let i = begin; i <= end; i+=step) {
      result += i;
   }
   return result;
}


sequenceSum(1, 5, 1);	// 15 (1 + 2 + 3 + 4 + 5)
sequenceSum(2, 6, 2);	// 12 (2 + 4 + 6)
sequenceSum(1, 5, 3);	// 5 (1 + 4)
```

<br>

## solution 03

```javascript
function sequenceSum(begin, end, step) {
   if (begin > end) {
      return 0;
   }
   return begin + sequenceSum(begin + step, end, step);
}


sequenceSum(1, 5, 1);	// 15 (1 + 2 + 3 + 4 + 5)
sequenceSum(2, 6, 2);	// 12 (2 + 4 + 6)
sequenceSum(1, 5, 3);	// 5 (1 + 4)
```

