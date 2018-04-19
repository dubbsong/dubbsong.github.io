---
layout: post
title: "bigTosmall.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

First to all, flat output '`array`'

to a one-dimensional array.

And then sort array in descending order.

<br>

## solution 01

```javascript
function bigToSmall(array) {
   return [].concat(...array).sort((a, b) => b - a).join(', ');
}


bigToSmall([[1, 2], [3, 4]]);	// 4, 3, 2, 1
bigToSmall([[1, 3, 5], [2, 4]]);	// 5, 4, 3, 2, 1
```

<br>

## solution 02

```javascript
const bigToSmall = array => [].concat(...array).sort((a, b) => b - a).join(', ');


bigToSmall([[1, 2], [3, 4]]);	// 4, 3, 2, 1
bigToSmall([[1, 3, 5], [2, 4]]);	// 5, 4, 3, 2, 1
```

<br>

## solution 03

```javascript
function bigToSmall(array) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      result = result.concat(array[i]);
   }
   return result.sort((a, b) => b - a).join(', ');
}


bigToSmall([[1, 2], [3, 4]]);	// 4, 3, 2, 1
bigToSmall([[1, 3, 5], [2, 4]]);	// 5, 4, 3, 2, 1
```

