---
layout: post
title: "evenLengthWords.js"
categories: dev
tags: algo
---

#### 반복문(for loop) + 조건문(if) + 배열(array) 알고리즘 문제

<br>

## problem

Write a function '`evenLengthWords`'

that takes an array of strings as an argument,

and returns an array of just the words

that have an even length.

<br>

## solution 01

```javascript
function evenLengthWords(array) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      if (array[i].length % 2 === 0) {
         result.push(array[i]);
      }
   }
   return result;
}


evenLengthWords(['Sam', 'Leo', 'Wassup', 'bro?']);	// ['Wassup', 'bro?']
```

<br>

## solution 02

```javascript
function evenLengthWords(array) {
   let result = [];
   
   for (let i of array) {
      if (i.length % 2 === 0) {
         result.push(i);
      }
   }
   return result;
}


evenLengthWords(['Sam', 'Leo', 'Wassup', 'bro?']);	// ['Wassup', 'bro?']
```

<br>

## solution 03

```javascript
function evenLengthWords(array) {
   return array.filter((a) => { if (a.length % 2 === 0) return a });
}


evenLengthWords(['Sam', 'Leo', 'Wassup', 'bro?']);	// ['Wassup', 'bro?']
```

