---
layout: post
title: "discoverOriginalPrice.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 기본 수학 알고리즘 문제

<br>

## problem

We need to write some code

to return the original price of a product,

the return type must be of type decimal

and the number must be rounded to two decimal places.

<br>

We will be given the sale price,

and the sale percentage,

our job is to figure out the original price.

<br>

## solution 01

```javascript
function discoverOriginalPrice(discountedPrice, salePercentage) {
   let percentage = salePercentage / 100;
   let originalPrice = discountedPrice / (1 - percentage);
   return Math.round(originalPrice * 100) / 100;
}


discoverOriginalPrice(90, 10);	// 100
discoverOriginalPrice(75, 25);	// 100
```

> `Math.round()` 메소드
>
> 부동 소수점 값을 가장 가까운 정수 값으로 반올림한다.

<br>

## solution 02

```javascript
function discoverOriginalPrice(discountedPrice, salePercentage) {
   return +(discountedPrice / (1 - salePercentage / 100)).toFixed(2);
}


discoverOriginalPrice(90, 10);	// 100
discoverOriginalPrice(75, 25);	// 100
```

> `.toFixed()` 메소드
>
> 소수의 자리수 길이를 제한한다.

<br>