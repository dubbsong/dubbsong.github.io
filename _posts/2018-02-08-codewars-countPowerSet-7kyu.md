---
layout: post
title: "countPowerSet.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 기본 수학 + 메소드(method) 활용 알고리즘 문제

<br>

## problem

You must create a function '`countPowerSet`' that takes an array,

and returns the number of subsets possible to create from that list.

<br>

In other words, counts the power set.

<br>

> `power set (멱집합)`
>
> 집합의 모든 부분 집합을 모은 집합.
>
> 유한 집합 S의 멱집합 P의 크기는 `P(S) = 2^S`

<br>

## solution 01

```javascript
function countPowerSet(array) {
   return Math.pow(2, array.length);
}


countPowerSet([1, 2, 3]);	// 8

// due to
// [[], [1], [2], [3], [1, 2], [1, 3], [2, 3], [1, 2, 3]]
```

> `Math.pow(base, exponent)` 메소드
>
> 지정된 숫자의 지정된 거듭제곱을 반환한다.
>
> `base`: 밑 (여러 번 곱할 수)
>
> `exponent`: 지수 (곱하는 횟수)

<br>

## solution 02

```javascript
function countPowerSet(array) {
   return 2 ** array.length;
}


countPowerSet([1, 2, 3]);	// 8

// due to
// [[], [1], [2], [3], [1, 2], [1, 3], [2, 3], [1, 2, 3]]
```

<br>

## solution 03

```javascript
function countPowerSet(array) {
   let result = 1;
   
   for (let i = 0; i < array.length; i++) {
      result = result * 2;
   }
   return result;
}


countPowerSet([1, 2, 3]);	// 8

// due to
// [[], [1], [2], [3], [1, 2], [1, 3], [2, 3], [1, 2, 3]]
```

