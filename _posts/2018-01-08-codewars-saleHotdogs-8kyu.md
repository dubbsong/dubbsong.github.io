---
layout: post
title: "saleHotdogs.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if/switch) + 불린(boolean) 알고리즘 문제

<br>

## problem

Complete function '`saleHotdogs`',

function accept 1 parameter 'n',

n is the number of customers to buy hotdogs,

different numbers have different prices,

return a number that the customer need

to pay how much money.

<br>

> n < 5: 100 (cents)
>
> n >= 5 && n < 10: 95 (cents)
>
> n >= 10: 90 (cents)

<br>

## solution 01

```javascript
function saleHotdogs(n) {
   if (n < 5) {
      return n * 100;
   } else if (n >= 5 && n < 10) {
      return n * 95;
   } else {
      return n * 90;
   }
}


saleHotdogs(4);	// 400
saleHotdogs(5);	// 475
saleHotdogs(9);	// 855
saleHotdogs(10);	// 900
```

<br>

## solution 02

```javascript
function saleHotdogs(n) {
   return n * (n < 5 ? 100 : n < 10 ? 95 : 90);
}


saleHotdogs(4);	// 400
saleHotdogs(5);	// 475
saleHotdogs(9);	// 855
saleHotdogs(10);	// 900
```

<br>

## solution 03

```javascript
const saleHotdogs = n => n * (n < 5 ? 100 : n < 10 ? 95 : 90);


saleHotdogs(4);	// 400
saleHotdogs(5);	// 475
saleHotdogs(9);	// 855
saleHotdogs(10);	// 900
```

<br>

## solution 04

```javascript
const saleHotdogs = n => {
   switch (true) {
      case n < 5: return n * 100;
      case n < 10: return n * 95;
      default: return n * 90;
   }
}


saleHotdogs(4);	// 400
saleHotdogs(5);	// 475
saleHotdogs(9);	// 855
saleHotdogs(10);	// 900
```

