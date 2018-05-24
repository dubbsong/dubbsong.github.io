---
layout: post
title: "averageScores.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Create a function that returns the average of an array of numbers,

rounded to the nearest whole number.

<br>

You are not allowed to use any loops.

(including for/in, while, and do/while loops)

<br>

## solution 01

```javascript
function averageScores(array) {
   const sum = array.reduce((a, b) => a + b, 0) / array.length;
   return Math.round(sum);
}


averageScores([1, 2, 3, 4]);	// 3
```

> `.reduce()` 메소드
>
> 왼쪽에서 오른쪽으로 이동하면서
>
> 배열의 각 요소마다 누적 계산값과 함께
>
> 함수를 적용해 하나의 값으로 줄인다.

<br>

> `Math.round()` 메소드
>
> 부동 소수점 값을 가장 가까운 정수 값으로 반올림한다.

<br>

## solution 02

```javascript
function averageScores(array) {
   return Math.round(array.reduce((a, b) => a + b, 0) / array.length);
}


averageScores([1, 2, 3, 4]);	// 3
```

