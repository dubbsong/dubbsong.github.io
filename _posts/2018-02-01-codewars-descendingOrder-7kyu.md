---
layout: post
title: "descendingOrder.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Your task is to make a function

that can take any non-negative integer

as a argument and return it

with its digits in descending order.

<br>

Essentially, rearrange the digits

to create the highest possible number.

<br>

## solution 01

```javascript
function descendingOrder(number) {
   return +number.toString().split('').sort().reverse().join('');
}


descendingOrder(1234);	// 4321
descendingOrder(3142);	// 4321
```

> `+`
>
> 문자열을 숫자로 변환한다.

<br>

> `.toString()` 메소드
>
> 숫자를 문자열로 변환한다.

<br>

## solution 02

```javascript
function descendingOrder(number) {
   return +number.toString().split('').sort((a, b) => b - a).join('');
}


descendingOrder(1234);	// 4321
descendingOrder(3142);	// 4321
```

<br>

## solution 03

```javascript
function descendingOrder(number) {
   return parseInt(number.toString().split('').sort((a, b) => b - a).join(''));
}


descendingOrder(1234);	// 4321
descendingOrder(3142);	// 4321
```

> `.parseInt()` 메소드
>
> 문자열을 정수로 변환한다.

<br>

> `.sort()` 메소드
>
> 배열의 요소를 적절한 위치에 정렬하고 배열을 반환한다.

<br>