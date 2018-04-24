---
layout: post
title: "mango.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 단순 계산 + 메소드 활용 알고리즘 문제

<br>

## problem

There's a '`3 for 2 (2 + 1)`' offer on mangoes.

For a given quantity and price,

calculate the total cost of the mangoes.

<br>

## solution 01

```javascript
function mango(quantity, price) {
   const free = quantity / 3;
   return (quantity - free) * price;
}


mango(3, 3);	// 6
mango(9, 5);	// 30
```

<br>

\* 자바스크립트의 부동 소수점 연산 오류를 생각하면

`Math.floor()` 메소드를 사용해야 한다.

<br>

\* 자바스크립트의 숫자(number)는

`내부적으로 64비트 부동 소수점 형식`을 지닌다.

<br>

> 214500 / 1.1 = 195000 (구글 계산기)
>
> 214500 / 1.1 = 195000 (네이버 계산기)
>
> 214500 / 1.1 = 194999.99999999997 (자바스크립트)

<br>

## solution 01(2)

```javascript
function mango(quantity, price) {
   const free = Math.floor(quantity / 3);
   return (quantity - free) * price;
}


mango(3, 3);	// 6
mango(9, 5);	// 30
```

<br>

## solution 02

```javascript
function mango(quantity, price) {
   return price * (quantity - (quantity / 3));
}


mango(3, 3);	// 6
mango(9, 5);	// 30
```



