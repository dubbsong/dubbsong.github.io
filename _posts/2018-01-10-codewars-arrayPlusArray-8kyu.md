---
layout: post
title: "arrayPlusArray.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 배열(array) 알고리즘 문제

<br>

## problem

I'm new to coding

and now I want to get the sum of two arrays.

Actually the sum of all their elements.

I'll appreciate for your help.

<br>

\* Each array includes only integer numbers.

\* Output is a number too.

<br>

> `.concat()` method
>
> const number = [8, 6, 8, 8];
>
> const string = ['ssup', 'bro?'];
>
> const all = number.concat(string);
>
> console.log(all);	// [ 8, 6, 8, 8, 'ssup', 'bro?' ]

<br>

## solution 01

```javascript
function arrayPlusArray(arr1, arr2) {
   return arr1.concat(arr2).reduce((a, b) => a + b);
}


arrayPlusArray([1, 2], [3, 4]);	// 10
```

<br>

## solution 02

```javascript
const arrayPlusArray = (arr1, arr2) => arr1.concat(arr2).reduce((a, b) => a + b);


arrayPlusArray([1, 2], [3, 4]);	// 10
```

<br>

## solution 03

```javascript
function arrayPlusArray(arr1, arr2) {
   let arr = [...arr1, ...arr2];
   return arr.reduce((a, b) => a + b);
}


arrayPlusArray([1, 2], [3, 4]);	// 10
```

