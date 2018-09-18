---
layout: post
title: "superSize.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 숫자(number) + 문자열(string) + 메소드 활용 알고리즘 문제

<br>

## problem

Write a function that rearranges an integer

into its largest possible value.

<br>

## solution 01

```javascript
function superSize(number) {
   return +number.toString().split('').sort().reverse().join('');
}


superSize(1234);			// 4321
console.log(typeof superSize(1234));	// number
superSize(2018);			// 8210
console.log(typeof superSize(2018));	// number
```

<br>

## solution 02

```javascript
function superSize(number) {
   return +number.toString().split('').sort((a, b) => b - a).join('');
}


superSize(1234);			// 4321
console.log(typeof superSize(1234));	// number
superSize(2018);			// 8210
console.log(typeof superSize(2018));	// number
```

<br>

## solution 03

```javascript
function superSize(number) {
   return parseInt(number.toString().split('').sort((a, b) => b - a).join());
}


superSize(1234);			// 4321
console.log(typeof superSize(1234));	// number
superSize(2018);			// 8210
console.log(typeof superSize(2018));	// number
```

<br>

## solution 04

```javascript
const superSize = number => parseInt(number.toString().split('').sort((a, b) => b - a).join(''));


superSize(1234);			// 4321
console.log(typeof superSize(1234));	// number
superSize(2018);			// 8210
console.log(typeof superSize(2018));	// number
```

