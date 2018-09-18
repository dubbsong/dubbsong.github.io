---
layout: post
title: "removeDuplicates.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Complete the function

that removes duplicates

from a list of numbers.

<br>

The order of the sequence needs to stay the same.

<br>

## solution 01

```javascript
function removeDuplicates(array) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      if (result.indexOf(array[i]) === -1) {
         result.push(array[i]);
      }
   }
   return result;
}


removeDuplicates([1, 1, 2]);	// [1, 2]
removeDuplicates([1, 2, 2]);	// [1, 2]
```

<br>

## solution 02

```javascript
function removeDuplicates(array) {
   return [...new Set(array)];
}


removeDuplicates([1, 1, 2]);	// [1, 2]
removeDuplicates([1, 2, 2]);	// [1, 2]
```

<br>

## solution 03

```javascript
const removeDuplicates = array => [...new Set(array)];


removeDuplicates([1, 1, 2]);	// [1, 2]
removeDuplicates([1, 2, 2]);	// [1, 2]
```

<br>

## solution 04

```javascript
function removeDuplicates(array) {
   return Array.from(new Set(array));
}


removeDuplicates([1, 1, 2]);	// [1, 2]
removeDuplicates([1, 2, 2]);	// [1, 2]
```

