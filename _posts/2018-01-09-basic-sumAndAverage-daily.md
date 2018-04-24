---
layout: post
title: "sumAndAverage.js"
categories: dev
tags: algo
---

#### 반복문(for loop) 활용 알고리즘 문제

<br>

## problem

Use the skeleton provided

to write a working implementation.

<br>

> Notes:
>
> Do not leave any functions in the skeleton unused.
>
> Test that your implementation works.

<br>

## solution

```javascript
function sum(numbers) {
   let result = 0;
   
   for (let i = 0; i < numbers.length; i++) {
      result += numbers[i];
   }
   return result;
}


function average(numbers) {
   return sum(numbers) / numbers.length;
}


sum([1, 2, 3, 4]);		// 10
average([1, 2, 3, 4]);	// 2.5
```

