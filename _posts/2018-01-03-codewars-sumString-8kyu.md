---
layout: post
title: "sumString.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 문자열(string) + 숫자(number) 변환 알고리즘 문제

<br>

## problem

Create a function

that takes 2 numbers in form of a string

as an input, and outputs the sum.

<br>

If either input is an empty string,

consider it as zero.

<br>

If both inputs are empty, output '0'.

<br>

## solution 01

```javascript
function sumString(string1, string2) {
   return ((string1 * 1) + (string2 * 1)) + '';
}


sumString('', '');	// '0' (string)
sumString('', '4');	// '4' (string)
sumString('4', '4');	// '8' (string)
```

<br>

## solution 02

```javascript
function sumString(string1, string2) {
   return String(Number(string1) + Number(string2));
}


sumString('', '');	// '0' (string)
sumString('', '4');	// '4' (string)
sumString('4', '4');	// '8' (string)
```

<br>

## solution 03

```javascript
const sumString = (string1, string2) => `${Number(string1) + Number(string2)}`;


sumString('', '');	// '0' (string)
sumString('', '4');	// '4' (string)
sumString('4', '4');	// '8' (string)
```



ㅇㅇ