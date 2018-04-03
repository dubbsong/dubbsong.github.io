---
layout: post
title: "squareOrSquareRoot.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) 알고리즘 문제

<br>

## problem

Write a method,

that will get an integer array as parameter

and will process every number from this array.

<br>

Return a new array with processing every number

of the input-array like this:

[4, 3, 9, 7, 2, 1] -> [2, 9, 3, 49, 4, 1]

<br>

> `Math.sqrt()` method
>
> Math.sqrt(2);	// 1.4142135623730951
>
> Math.sqrt(4);	// 2
>
> Math.sqrt(9);	// 3
>
> Math.sqrt(49);	// 7
>
> Math.sqrt(64);	// 8

<br>

## solution 01

```javascript
function squareOrSquareRoot(array) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      let x = Math.sqrt(array[i]);
      
      if (x % 1 === 0) {
         result.push(x);
      } else {
         result.push(array[i] * array[i]);
      }
   }
   return result;
}


squareOrSquareRoot([4, 3, 9, 7, 1]);	// [2, 9, 3, 49, 1]
```

<br>

## solution 02

```javascript
function squareOrSquareRoot(array) {
   return array.map(a => {
      const x = Math.sqrt(a);
      return (x % 1 === 0) ? x : a * a;
   })
}


squareOrSquareRoot([4, 3, 9, 7, 1]);	// [2, 9, 3, 49, 1]
```

