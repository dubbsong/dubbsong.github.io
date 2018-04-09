---
layout: post
title: "rentalCarCost.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) 알고리즘 문제

<br>

## problem

`Every day` you rent the car costs `$40`.

If you rent the car for `7 or more days`,

you get `$50` off your total.

<br>

Alternatively,

if you rent the car for `3 or more days`,

you get `$20` off your total.

<br>

Write a code that

gives out the total amount for different days.

<br>

## solution 01

```javascript
function rentalCarCost(day) {
   let total = day * 40;
   
   if (day >= 7) {
      total -= 50;
   } else if (day >= 3) {
      total -= 20;
   }
   return total;
}


rentalCarCost(1);	// 40
rentalCarCost(2);	// 80
rentalCarCost(3);	// 100
rentalCarCost(6);	// 220
rentalCarCost(7);	// 230
```

<br>

## solution 02

```javascript
const rentalCarCost = day => day * 40 - (day >= 7 ? 50 : day >= 3 ? 20 : 0);


rentalCarCost(1);	// 40
rentalCarCost(2);	// 80
rentalCarCost(3);	// 100
rentalCarCost(6);	// 220
rentalCarCost(7);	// 230
```

<br>

## solution 03

```javascript
const rentalCarCost = day => day * 40 - (day > 6 ? 50 : day > 2 ? 20 : 0);


rentalCarCost(1);	// 40
rentalCarCost(2);	// 80
rentalCarCost(3);	// 100
rentalCarCost(6);	// 220
rentalCarCost(7);	// 230
```

