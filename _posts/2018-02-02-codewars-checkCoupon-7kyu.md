---
layout: post
title: "checkCoupon.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function called '`checkCoupon`'

to verify that a coupon is valid and not expired.

<br>

## solution 01

```javascript
function checkCoupon(enteredCode, correctCode, currentDate, expirationDate) {
   currentDate = new Date(currentDate);
   expirationDate = new Date(expirationDate);
   return enteredCode === correctCode && currentDate <= expirationDate;
}


checkCoupon('1234', '1234', 'Apr 1, 2018', 'Dec 31, 2018');	// true
checkCoupon('5678', '1234', 'Apr 1, 2018', 'Dec 31, 2018');	// false
```

> `new Date()` 메소드
>
> Date 객체를 사용해서 날짜 비교 및 경과 시간 계산을 할 수 있다.

<br>

## solution 02

```javascript
function checkCoupon(enteredCode, correctCode, currentDate, expirationDate) {
   currentDate = Date.parse(currentDate);
   expirationDate = Date.parse(expirationDate);
   return enteredCode === correctCode && currentDate <= expirationDate;
}


checkCoupon('1234', '1234', 'Apr 1, 2018', 'Dec 31, 2018');	// true
checkCoupon('5678', '1234', 'Apr 1, 2018', 'Dec 31, 2018');	// false
```

> `Date.parse(dateString)` 메소드
>
> 시간을 나타내는 문자열이 주어지면 parse()는 시간 값을 반환한다.

<br>