---
layout: post
title: "summy.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function that takes a string

which has integers inside it separated by spaces,

and your task is to convert each integer in the string

into an integer and return their sum.

<br>

## solution 01

```javascript
function summy(string) {
   return string.split(' ').map(Number).reduce((a, b) => a + b, 0);
}


summy('1 2 3');	// 6
summy('1 2 3 4');	// 10
```

> `.split()` 메소드
>
> 문자열을 부분 문자열로 분할해서 배열로 반환한다.

<br>

> `.map()` 메소드
>
> 배열 내 모든 요소 각각에 대하여
>
> 제공된 함수(callback)를 호출하고,
>
> 그 결과를 모아서 새로운 배열을 반환한다.

<br>

> `.reduce()` 메소드
>
> 왼쪽에서 오른쪽으로 이동하면서
>
> 배열의 각 요소마다 누적 계산값과 함께
>
> 함수를 적용해 하나의 값으로 줄인다.

<br>

## solution 02

```javascript
function summy(string) {
   string = string.split(' ');
   let result = 0;
   
   for (let i = 0; i < string.length; i++) {
      result += parseInt(string[i]);
   }
   return result;
}


summy('1 2 3');	// 6
summy('1 2 3 4');	// 10
```

> `parseInt()` 메소드
>
> 문자열을 파싱하고, 특정 radix(진수)의 정수를 반환한다.

<br>

## solution 03

```javascript
function summy(string) {
   return string.split(' ').reduce((a, b) => a + +b, 0);
}


summy('1 2 3');	// 6
summy('1 2 3 4');	// 10
```



