---
layout: post
title: "sumMixedArray.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Given an array of integers as strings and numbers,

return the sum of the array values as if all were numbers.

<br>

Return your answer as a number.

<br>

## solution 01

```javascript
function sumMixedArray(array) {
   let result = 0;
   
   for (let i = 0; i < array.length; i++) {
      result += parseInt(array[i]);
   }
   return result;
}


sumMixedArray(1, 2, '3', '4');	// 10
sumMixedArray(8, 6, '8', '8');	// 30
```

> `parseInt()` 메소드
>
> 문자열을 파싱(해석)해서 정수(integer)를 반환한다.

<br>

## solution 02

```javascript
function sumMixedArray(array) {
   return array.map(a => +a).reduce((a, b) => a + b);
}


sumMixedArray(1, 2, '3', '4');	// 10
sumMixedArray(8, 6, '8', '8');	// 30
```

<br>

## solution 03

```javascript
function sumMixedArray(array) {
   return array.reduce((a, b) => a + Number(b), 0);
}


sumMixedArray(1, 2, '3', '4');	// 10
sumMixedArray(8, 6, '8', '8');	// 30
```

<br>

## solution 04

```javascript
function sumMixedArray(array) {
   return array.reduce((a, b) => a + (+b), 0);
}


sumMixedArray(1, 2, '3', '4');	// 10
sumMixedArray(8, 6, '8', '8');	// 30
```

