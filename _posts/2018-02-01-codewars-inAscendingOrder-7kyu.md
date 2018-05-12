---
layout: post
title: "inAscendingOrder.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Your function receives

an array of positive integers as input.

<br>

Your task is to determine

whether the numbers are in ascending order.

<br>

## solution 01

```javascript
function inAscendingOrder(array) {
   for (let i = 0; i < array.length - 1; i++) {
      if (array[i] > array[i + 1]) {
         return false;
      }
   }
   return true;
}


inAscendingOrder([1, 2, 3, 4]);	// true
inAscendingOrder([1, 4, 7, 9]);	// true
inAscendingOrder([1, 4, 2, 3]);	// false
```

<br>

## solution 02

```javascript
function inAscendingOrder(array) {
   for (let i = 1; i < array.length; i++) {
      if (array[i] < array[i - 1]) {
         return false;
      }
   }
   return true;
}


inAscendingOrder([1, 2, 3, 4]);	// true
inAscendingOrder([1, 4, 7, 9]);	// true
inAscendingOrder([1, 4, 2, 3]);	// false
```

<br>

## solution 03

```javascript
function inAscendingOrder(array) {
   return array.join('') === array.sort((a, b) => a - b).join('');
}


inAscendingOrder([1, 2, 3, 4]);	// true
inAscendingOrder([1, 4, 7, 9]);	// true
inAscendingOrder([1, 4, 2, 3]);	// false
```

> `.join()` 메소드
>
> 배열의 모든 요소를 연결해 하나의 문자열로 만들고, 문자열을 반환한다.

<br>

> `.sort()` 메소드
>
> 배열의 요소를 적절한 위치에 정렬하고, 배열을 반환한다.

<br>