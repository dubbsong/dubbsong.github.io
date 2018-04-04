---
layout: post
title: "fakeBinary.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 불린(boolean) 알고리즘 문제

<br>

## problem

Given a string of digits,

you should replace any digit below 5 with '0'

and any digit 5 and above with '1'.

<br>

Return the resulting string.

<br>

## solution 01

```javascript
function fakeBinary(string) {
   let result = [];
   
   for (let i = 0; i < string.length; i++) {
      if (string[i] >= 0 && string[i] < 5) {
         result.push(0);
      } else {
         result.push(1);
      }
   }
   return result.join('');
}


fakeBinary('123456789');	// '000011111'
fakeBinary('192837465');	// '010101011'
```

<br>

## solution 02

```javascript
function fakeBinary(string) {
   return string.split('').map(a => a < 5 ? 0 : 1).join('');
}


fakeBinary('123456789');	// '000011111'
fakeBinary('192837465');	// '010101011'
```

<br>

## solution 03

```javascript
function fakeBinary(string) {
   return string.replace(/[1234]/g, '0').replace(/[56789]/g, '1');
}


fakeBinary('123456789');	// '000011111'
fakeBinary('192837465');	// '010101011'
```

<br>

## solution 04

```javascript
function fakeBinary(string) {
   return string.replace(/\d/g, a => a < 5 ? 0 : 1);
}


fakeBinary('123456789');	// '000011111'
fakeBinary('192837465');	// '010101011'
```

