---
layout: post
title: "smallestValue.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function that can return the smallest value of an array

or the index of that value.

<br>

The function's 2nd parameter will tell whether

it should return `the value` or `the index`.

<br>

Assume the first parameter will always be an array filled

with at least 1 number and no duplicates.

<br>

Assume the second parameter will be a string holding

one of two values: `value` and `index`.

<br>

## solution 01

```js
function smallestValue(array, toReturn) {
   let result = 0;
   
   if (toReturn === 'value') {
      result = Math.min(...array);
   } else {
      result = array.indexOf(Math.min(...array));
   }
   return result;
}


smallestValue([1, 2, 3, 4], 'value');	// 1
smallestValue([1, 2, 3, 4], 'index');	// 0
```

> `.indexOf()` 메소드
>
> 일치하는 인덱스를 반환하고, 일치하는 값이 없으면 -1을 반환한다.

<br>

## solution 02

```js
function smallestValue(array, toReturn) {
   if (toReturn === 'value') return Math.min(...array);
   if (toReturn === 'index') return array.indexOf(Math.min(...array));
}


smallestValue([1, 2, 3, 4], 'value');	// 1
smallestValue([1, 2, 3, 4], 'index');	// 0
```

<br>

## solution 03

```js
function smallestValue(array, toReturn) {
   let min = Math.min(...array);
   return toReturn === 'value' ? min : array.indexOf(min);
}


smallestValue([1, 2, 3, 4], 'value');	// 1
smallestValue([1, 2, 3, 4], 'index');	// 0
```

