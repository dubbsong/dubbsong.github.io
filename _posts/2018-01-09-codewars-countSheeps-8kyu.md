---
layout: post
title: "countSheeps.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 조건문(if) + 불린(boolean) 알고리즘 문제

<br>

## problem

Consider an arry of sheep

where some sheep may be missing from their place.

<br>

We need a function

that counts the number of sheep present in the array.

(true means present)

<br>

## an array

```javascript
const array = [
   true, true, true, false,
   true, true, true, true,
   true, false, true, false,
   true, false, false, true,
   true, true, true, true,
   false, false, true, true
];
```



<br>

## solution 01

```javascript
function countSheeps(array) {
   let result = 0;
   
   for (let i = 0; i < array.length; i++) {
      if (array[i] === true) {
         result += 1;
      }
   }
   return += 1;
}


countSheeps(array);	// 17
```

<br>

## solution 02

```javascript
const countSheeps = array => array.filter(a => a).length;


countSheeps(array);	// 17
```

<br>

## solution 03

```javascript
function countSheeps(array) {
   return array.filter(Boolean).length;
}


countSheeps(array);	// 17
```

