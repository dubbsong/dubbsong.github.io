---
layout: post
title: "twoOldestAges.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

The two oldest ages function needs to be completed.

<br>

It should take an array of numbers as its argument

and return the two highest numbers within the array.

<br>

The returned value should be an array in the format.

The order of the numbers passed in could be any order.

The array will always include at least 2 items.

<br>

## solution 01

```javascript
function twoOldestAges(ages) {
   return ages.sort((a, b) => a - b).slice(-2);
}


twoOldestAges([4, 2, 1, 8]);	// [4, 8]
```

> `.sort()` 메소드
>
> 배열의 요소를 적절한 위치에 정렬하고, 배열을 반환한다.

<br>

> `.slice()` 메소드
>
> 문자열의 일부를 추출하면서 새로운 문자열을 반환한다.

<br>

## solution 02

```javascript
function twoOldestAges(ages) {
   const sortAges = ages.sort((a, b) => b - a);
   return [sortAges[1], sortAges[0]];
}


twoOldestAges([4, 2, 1, 8]);	// [4, 8]
```

