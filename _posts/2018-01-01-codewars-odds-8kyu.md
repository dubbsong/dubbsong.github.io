---
layout: post
title: "odds.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 배열(array) + 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Return the odds from a list.

<br>

## solution 01

```javascript
function odds(array) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      if (array[i] % 2 !== 0) {
         result.push(array[i]);
      }
   }
   return result;
}


odds([1, 2, 3, 4]);	// [1, 3]
```

<br>

## solution 02

```javascript
function odds(array) {
   return array.filter(a => a % 2 !== 0);
}


odds([1, 2, 3, 4]);	// [1, 3]
```

<br>

## solution 03

```javascript
function odds(array) {
   return array.filter(a => a % 2);
}


odds([1, 2, 3, 4]);	// [1, 3]
```

<br>

## solution 04

```javascript
const odds = array => array.filter(a => a % 2);


odds([1, 2, 3, 4]);	// [1, 3]
```

