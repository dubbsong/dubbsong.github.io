---
layout: post
title: "countBy.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) 알고리즘 문제

<br>

## problem

Create a function with two arguments

that will return a list of length(num2)

with multiples of 'num1'.

<br>

## solution

```javascript
function countBy(num1, num2) {
   let result = [];
   
   for (let i = 1; i <= num2; i++) {
      result.push(num1 * i);
   }
   return result;
}


countBy(1, 5);	// [1, 2, 3, 4, 5]
countBy(2, 5);	// [2, 4, 6, 8, 10]
```

