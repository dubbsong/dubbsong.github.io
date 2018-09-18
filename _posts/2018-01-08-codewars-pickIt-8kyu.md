---
layout: post
title: "pickIt.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Coding in function '`pickIt`',

function accept 1 parameter '`array`'.

<br>

If element is odd number,

push it to array '`odd`'.

If it's a even number,

push it to array '`even`'.

<br>

## solution 01

```javascript
function pickIt(array) {
   let odd = [];
   let even = [];
   
   for (let i = 0; i < array.length; i++) {
      if (array[i] % 2 !== 0) {
         odd.push(array[i]);
      } else {
         even.push(array[i]);
      }
   }
   return [odd, even];
}


pickIt([1, 2, 3, 4]);	// [[1, 3], [2, 4]]
pickIt([10, 20, 30]);	// [[], [10, 20, 30]]
```

<br>

## solution 02

```javascript
function pickIt(array) {
   let odd = [];
   let even = [];
   
   for (let i of array) {
      if (i % 2 !== 0) {
         odd.push(i);
      } else {
         even.push(i);
      }
   }
   return [odd, even];
}


pickIt([1, 2, 3, 4]);	// [[1, 3], [2, 4]]
pickIt([10, 20, 30]);	// [[], [10, 20, 30]]
```

<br>

## solution 03

```javascript
function pickIt(array) {
   let odd = [];
   let even = [];
   
   for (let i of array) {
      (i % 2 ? odd : even).push(i);
   }
   return [odd, even];
}


pickIt([1, 2, 3, 4]);	// [[1, 3], [2, 4]]
pickIt([10, 20, 30]);	// [[], [10, 20, 30]]
```

