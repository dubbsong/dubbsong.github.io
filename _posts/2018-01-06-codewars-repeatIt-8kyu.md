---
layout: post
title: "repeatIt.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 불린(boolean) + 반복문(for loop) + 메소드 활용 알고리즘 문제

<br>

## problem

Create a function

that takes a string and an integer '`n`'.

<br>

The function should return a string

that repeats the input string

'`n`' number of times.

<br>

If anything other than a string is passed in

you should return '`Not a string`'.

<br>

## solution 01

```javascript
function repeatIt(str, n) {
   let result = '';
   
   for (let i = 0; i < n; i++) {
      if (typeof str === 'string') {
         result += str;
      } else {
         return `Not a string`;
      }
   }
   return result;
}


repeatIt('ssup', 4);	// ssupssupssupssup
repeatIt('????', 4);	// ????????????????
```

<br>

## solution 02

```javascript
function repeatIt(str, n) {
   if (typeof str === 'string') {
      return string.repeat(n);
   } else {
      return `Not a string`;
   }
}


repeatIt('ssup', 4);	// ssupssupssupssup
repeatIt('????', 4);	// ????????????????
```

<br>

## solution 03

```javascript
function repeatIt(str, n) {
   return typeof str === 'string' ? str.repeat(n) : `Not a string`;
}


repeatIt('ssup', 4);	// ssupssupssupssup
repeatIt('????', 4);	// ????????????????
```

<br>

## solution 04

```javascript
const repeatIt = (str, n) => typeof str === 'string' ? string.repeat(n) : `Not a string`;


repeatIt('ssup', 4);	// ssupssupssupssup
repeatIt('????', 4);	// ????????????????
```

