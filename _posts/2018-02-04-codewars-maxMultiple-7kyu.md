---
layout: post
title: "maxMultiple.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 기본 수학 알고리즘 문제

<br>

## problem

Given a `divisor` and a `bound`,

find the largest integer `N`.

<br>

> Conditions:
>
> N is divisible by divisor.
>
> N is less than or equal to bound.
>
> N is greater than 0.

<br>

> Notes:
>
> The parameters passed to the function are only positive values.
>
> It's guaranteed that a divisor is found.

<br>

## solution 01

```javascript
function maxMultiple(divisor, bound) {
   return bound - bound % divisor;
}


maxMultiple(3, 10);	// 9
maxMultiple(7, 20);	// 14
maxMultiple(10, 1);	// 0
```

<br>

## solution 02

```javascript
function maxMultiple(divisor, bound) {
   return Math.floor(bound / divisor) * divisor;
}


maxMultiple(3, 10);	// 9
maxMultiple(7, 20);	// 14
maxMultiple(10, 1);	// 0
```

> `Math.floor()` 메소드
>
> 가장 가까운 정수로 버림한 다음, 결과를 반환한다.

<br>

## solution 03

```javascript
function maxMultiple(divisor, bound) {
   while (bound % divisor) {
      bound -= 1;
   }
   return bound;
}


maxMultiple(3, 10);	// 9
maxMultiple(7, 20);	// 14
maxMultiple(10, 1);	// 0
```

