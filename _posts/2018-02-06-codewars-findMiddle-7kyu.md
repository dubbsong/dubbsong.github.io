---
layout: post
title: "findMiddle.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

As a part of this Kata,

you need to create a function

that when provided with a triplet,

returns the index of the numerical element

that lies between the other two elements.

<br>

The input to the function will be

an array of three distinct numbers.

<br>

## solution 01

```javascript
function findMiddle(array) {
   return array.indexOf(array.concat().sort((a, b) => a - b)[1]);
}


findMiddle([1, 2, 3]);	// 1
findMiddle([2, 1, 3]);	// 0
```

> `.indexOf()` 메소드
>
> 일치하는 인덱스를 반환하고, 존재하지 않으면 -1을 반환한다.

<br>

> `.concat()` 메소드
>
> 주어진 배열을 기존 배열에 합쳐서 새로운 배열을 반환한다.

<br>

## solution 02

```javascript
function findMiddle(array) {
	return array.indexOf(array.slice().sort((a, b) => a - b)[1]);
}


findMiddle([1, 2, 3]);	// 1
findMiddle([2, 1, 3]);	// 0
```

> `.slice()` 메소드
>
> 문자열의 일부를 추출하면서 새로운 배열을 반환한다.

<br>