---
layout: post
title: "powerOfTwo.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop / while loop) + 메소드 활용 알고리즘 문제

<br>

## problem

Complete the function

that takes a non-negative integer '`n`' as input,

and returns a list of all the `powers of 2`

with the exponent ranging from 0 to 'n'.

<br>

> Math.pow(4, 2);	// 16
>
> Math.pow(4, 0.5);	// 2 (제곱근 4)
>
> Math.pow(-4, 2);	// 16 (양수)

<br>

## solution 01

```javascript
function powerOfTwo(n) {
   let result = [1];
   
   for (let i = 1; i <= n; i++) {
      result.push(result[i - 1] * 2);
   }
   return result;
}


powerOfTwo(0);	// [1]
powerOfTwo(1);	// [1, 2]
powerOfTwo(4);	// [1, 2, 4, 8, 16]
```

<br>

## solution 02

```javascript
function powerOfTwo(n) {
   let result = [];
   
   for (let i = 0; i <= n; i++) {
      result.push(Math.pow(2, i));
   }
   return result;
}


powerOfTwo(0);	// [1]
powerOfTwo(1);	// [1, 2]
powerOfTwo(4);	// [1, 2, 4, 8, 16]
```

<br>

## solution 03

```javascript
function powerOfTwo(n) {
   let result = [];
   let i = 0;
   
   while (i <= n) {
      result.push(Math.pow(2, i));
      i += 1;
   }
   return result;
}


powerOfTwo(0);	// [1]
powerOfTwo(1);	// [1, 2]
powerOfTwo(4);	// [1, 2, 4, 8, 16]
```

<br>

## solution 04

```javascript
const powerOfTwo = n => [...Array(n + 1)].map((element, index) => Math.pow(2, index));


powerOfTwo(0);	// [1]
powerOfTwo(1);	// [1, 2]
powerOfTwo(4);	// [1, 2, 4, 8, 16]
```



