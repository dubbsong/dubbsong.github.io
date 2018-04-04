---
layout: post
title: "reverseSequence.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) 알고리즘 문제

<br>

## problem

Get the number 'num' to return the reversed sequence from num to 1.

<br>

## solution 01

```javascript
function reverseSequence(num) {
   let result = [];
   
   for (let i = num; i >= 1; i--) {
      result.push(i);
   }
   return result;
}


reverseSequence(4);	// [4, 3, 2, 1]
```

<br>

## solution 02

```javascript
function reverseSequence(num) {
   let result = [];
   
   for (let i = num; i >= 1; i--) {
      result.push(num--);
   }
   return result;
}


reverseSequence(4);	// [4, 3, 2, 1]
```

<br>

## solution 03

```javascript
const reverseSequence = length => Array.from({length}, () => length--);


reverseSequence(4);	// [4, 3, 2, 1]
```

