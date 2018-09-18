---
layout: post
title: "formatMoney.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

4 needs to become $4.00

4.1 needs to become $4.10

<br>

> `.toFixed()` method
>
> let num = 5.56789;
>
> num.toFixed(2);	// 5.57

<br>

## solution 01

```javascript
function formatMoney(amount) {
   return '$' + amount.toFixed(2);
}


formatMoney(4);		// $4.00
formatMoney(4.1);	// $4.10
```

<br>

## solution 02

```javascript
function formatMoney(amount) {
   return `$${amount.toFixed(2)}`;
}


formatMoney(4);		// $4.00
formatMoney(4.1);	// $4.10
```

<br>

## solution 03

```javascript
const formatMoney = amount => `$${amount.toFixed(2)}`;


formatMoney(4);		// $4.00
formatMoney(4.1);	// $4.10
```



