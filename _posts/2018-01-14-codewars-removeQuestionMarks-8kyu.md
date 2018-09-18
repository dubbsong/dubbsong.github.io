---
layout: post
title: "removeQuestionMarks.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) 알고리즘 문제

<br>

## problem

Write function '`removeQuestionMarks`'

which removes all question marks

from a given string.

<br>

## solution 01

```javascript
function removeQuestionMarks(string) {
   let result = [];
   
   for (let i = 0; i < string.length; i++) {
      if (string[i] !== '?') {
         result.push(string[i]);
      }
   }
   return result.join('');
}


removeQuestionMarks('Wassup bro??');	// Wassup bro
```

<br>

## solution 02

```javascript
function removeQuestionMarks(string) {
   const splitted = string.split('');
   let result = '';
   
   for (let i = 0; i < string.length; i++) {
      if (splitted[i] === '?') {
         splitted[i] = '';
      }
   }
   
   for (let j = 0; j < splitted.length; j++) {
      result += splitted[j];
   }
   return result;
}


removeQuestionMarks('Wassup bro??');	// Wassup bro
```

<br>

## solution 03

```javascript
function removeQuestionMarks(string) {
   return string.replace(/\?/g, '');
}


removeQuestionMarks('Wassup bro??');	// Wassup bro
```

<br>

## solution 04

```javascript
const removeQuestionMarks = string => string.replace(/\?/g, '');


removeQuestionMarks('Wassup bro??');	// Wassup bro
```

<br>

## solution 05

```javascript
function removeQuestionMarks(string) {
   return string.split('?').join('');
}


removeQuestionMarks('Wassup bro??');	// Wassup bro
```

