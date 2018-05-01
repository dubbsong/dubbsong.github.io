---
layout: post
title: "rowSumOdd.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 기본 수학 알고리즘 문제

<br>

## problem

Given the triangle of consecutive odd number:

<br>

​             1

​          3     5

​       7     9    11

   13    15    17    19

21    23    25    27    29

...

<br>

Calculate the row sums of this triangle

from the row index (starting at index 1).

<br>

## solution 01

```javascript
function rowSumOdd(n) {
   return n * n * n;
}


rowSumOdd(1);	// 1
rowSumOdd(2);	// 8 (3 + 5)
rowSumOdd(3);	// 27
rowSumOdd(42);	// 74088
```

<br>

## solution 02

```javascript
function rowSumOdd(n) {
   return Math.pow(n, 3);
}


rowSumOdd(1);	// 1
rowSumOdd(2);	// 8 (3 + 5)
rowSumOdd(3);	// 27
rowSumOdd(42);	// 74088
```

> `Math.pow()` 메소드
>
> 지정된 숫자의 지정된 거듭제곱을 반환한다.

<br>

## solution 03

```javascript
function rowSumOdd(n) {
   return n ** 3;
}


rowSumOdd(1);	// 1
rowSumOdd(2);	// 8 (3 + 5)
rowSumOdd(3);	// 27
rowSumOdd(42);	// 74088
```

