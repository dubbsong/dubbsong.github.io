---
layout: post
title: "binaryArrayToNumber.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Given an array of one's and zero's

convert the equivalent binary value to an integer.

<br>

`[0, 0, 0, 1]` is treated as `0001`

which is the binary representation of 1.

<br>

## solution 01

```javascript
function binaryArrayToNumber(array) {
   let result = '';
   
   for (let i = 0; i < array.length; i++) {
      result += array[i];
   }
   return parseInt(result, 2);
}


binaryArrayToNumber([0, 0, 0, 1]);	// 1
binaryArrayToNumber([0, 0, 1, 0]);	// 2
binaryArrayToNumber([0, 0, 1, 1]);	// 3
binaryArrayToNumber([1, 1, 1, 1]);	// 15
```

> `parseInt()` 메소드
>
> 문자열을 파싱하고, 특정 radix(진수)의 정수를 반환한다.

<br>

## solution 02

```javascript
function binaryArrayToNumber(array) {
   return parseInt(array.join(''), 2);
}


binaryArrayToNumber([0, 0, 0, 1]);	// 1
binaryArrayToNumber([0, 0, 1, 0]);	// 2
binaryArrayToNumber([0, 0, 1, 1]);	// 3
binaryArrayToNumber([1, 1, 1, 1]);	// 15
```

