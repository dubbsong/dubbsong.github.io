---
layout: post
title: "rangeSum.js"
categories: dev
tags: algo
---

#### 조건문(if) + 반복문(for loop) 알고리즘 문제

<br>

## problem

Create a sum function that accepts two parameters,

start and end:

sum should compute the sum of the numbers

from start to end.

<br>

> sum(3, 5);	// 3 + 4 + 5 = 12
>
> sum(3, 6);	// 3 + 4 + 5 + 6 = 18

<br>

What happens if start is larger than end?

Modify sum to check for this case and,

when found, swap the start and end arguments.

<br>

## solution 01

```javascript
function sum(start, end) {
   let result = 0;
   
   if (start < end) {
      for (let i = start; i <= end; i++) {
         result += i;
      }
      return result;
   }
   
   if (start > end) {
      for (let j = end; j <= start; j++) {
         result += j;
      }
      return result;
   }
}


sum(2, 7);	// 27
sum(3, 5);	// 12
sum(8, 6);	// 21
```

<br>

## solution 02

```javascript
function sum(start, end) {
   return end > start ? end*(end+1)/2 - start*(start-1)/2 : start*(start+1)/2 - end*(end-1)/2;
}
```



