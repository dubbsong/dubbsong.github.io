---
layout: post
title: "digitize.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 숫자(number) + 문자열(string) 알고리즘 문제

<br>

## problem

You have to return the digits of this number

within an array in reverse order.

<br>

> Input: 12345 (number)
>
> Output: [5, 4, 3, 2, 1] (array / reverse)

<br>

## solution 01

```javascript
const numbers = 12345;


function digitize(numbers) {
   return numbers.toString().split('').reverse().map(Number);
}


digitize(numbers);	// [5, 4, 3, 2, 1]
```

<br>

## solution 02

```javascript
const numbers = 12345;


function digitize(numbers) {
   return String(numbers).split('').reverse().map(Number);
}


digitize(numbers);	// [5, 4, 3, 2, 1]
```

<br>

## solution 03

```javascript
const numbers = 12345;


function digitize(numbers) {
   return (numbers + '').split('').reverse().map(Number);
}


digitize(numbers);	// [5, 4, 3, 2, 1]
```

<br>

## solution 04

```javascript
const numbers = 12345;


function digitize(numbers) {
   return Array.from(String(numbers), Number).reverse();
}


digitize(numbers);	// [5, 4, 3, 2, 1]
```





