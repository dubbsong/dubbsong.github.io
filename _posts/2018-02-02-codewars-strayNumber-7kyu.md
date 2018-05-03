---
layout: post
title: "strayNumber.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

You are given an odd-length array of integers,

in which all of them are the same,

except for one single number.

<br>

Complete the method which accepts such an array,

and returns that single different number.

<br>

## solution 01

```javascript
function strayNumber(numbers) {
   const sort = numbers.sort();
   
   if (sort[0] !== sort[1]) {
      return sort[0];
   } else {
      return sort[sort.length - 1];
   }
}


strayNumber([1, 2, 1, 1]);	// 2
strayNumber([3, 2, 3, 3]);	// 2
```

> `.sort()` 메소드
>
> 배열의 요소를 적절한 위치에 정렬하고 배열을 반환한다.

<br>

## solution 02

```javascript
function strayNumber(numbers) {
   const sort = numbers.sort((a, b) => a - b);
   return sort[0] !== sort[1] ? sort[0] : sort[sort.length - 1];
}


strayNumber([1, 2, 1, 1]);	// 2
strayNumber([3, 2, 3, 3]);	// 2
```

