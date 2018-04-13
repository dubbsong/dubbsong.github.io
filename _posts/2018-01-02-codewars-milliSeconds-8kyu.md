---
layout: post
title: "milliSeconds.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 시간 환산 알고리즘 문제

<br>

## problem

Clock shows (after midnight)

> h: hours (시간)
>
> m: minutes (분)
>
> s: seconds (초)

<br>

Your task is to make '`milliSeconds`' function

which returns time converted to milliseconds.

<br>

> millisecond: 1000분의 1초

<br>

## solution 01

```javascript
function milliSeconds(h, m, s) {
   return (h * 3600 + m * 60 + s) * 1000;
}


milliSeconds(0, 0, 0);	// 0
milliSeconds(0, 0, 1);	// 1000
milliSeconds(0, 1, 0);	// 60000
milliSeconds(1, 0, 0);	// 3600000
```

<br>

## solution 02

```javascript
const milliSeconds = (h, m, s) => (h * 3600 + m * 60 + s) * 1000;


milliSeconds(0, 0, 0);	// 0
milliSeconds(0, 0, 1);	// 1000
milliSeconds(0, 1, 0);	// 60000
milliSeconds(1, 0, 0);	// 3600000
```

<br>

## solution 03

```javascript
const milliSeconds = (h, m, s) => ((h * 60 + m) * 60 + s) * 1000;


milliSeconds(0, 0, 0);	// 0
milliSeconds(0, 0, 1);	// 1000
milliSeconds(0, 1, 0);	// 60000
milliSeconds(1, 0, 0);	// 3600000
```

<br>

## solution 04

```javascript
function milliSeconds(h, m, s) {
   let result = 0;
   
   result = result + s * 1000;
   result = result + m * 60000;
   result = result + h * 3600000;
   return result;
}


milliSeconds(0, 0, 0);	// 0
milliSeconds(0, 0, 1);	// 1000
milliSeconds(0, 1, 0);	// 60000
milliSeconds(1, 0, 0);	// 3600000
```

