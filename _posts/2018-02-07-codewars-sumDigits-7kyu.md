---
layout: post
title: "sumDigits.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function named '`sumDigits`'

which takes a number as input

and return the sum of the absolute value

of each of the number's decimal digits.

<br>

## solution 01

```javascript
function sumDigits(number) {
   return Math.abs(number).toString().split('').reduce((a, b) => a + +b, 0);
}


sumDigits(10);	// 1
sumDigits(99);	// 18
sumDigits(-32);	// 5
```

> `Math.abs()` 메소드
>
> 주어진 숫자의 절대값을 반환한다.

<br>

> `.toString()` 메소드
>
> 숫자를 문자열로 반환한다.

<br>

> `.split()` 메소드
>
> 문자열을 부분 문자열로 분할해서 배열로 반환한다.

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
function sumDigits(number) {
   number = Math.abs(number).toString();
   let = result = 0;
   
   for (let i = 0; i < number.length; i++) {
      result += parseInt(number[i]);
   }
   return result;
}


sumDigits(10);	// 1
sumDigits(99);	// 18
sumDigits(-32);	// 5
```

> `parseInt()` 메소드
>
> 문자열을 파싱하고, 특정 radix(진수)의 정수를 반환한다.

<br>

## solution 03

```javascript
function sumDigits(number) {
   return String(number).replace('-', '').split('').reduce((a, b) => a + Number(b), 0);
}


sumDigits(10);	// 1
sumDigits(99);	// 18
sumDigits(-32);	// 5
```

> `.replace()` 메소드
>
> 어떤 패턴에 일치하는 부분이, 교체된 새로운 문자열을 반환한다.

<br>