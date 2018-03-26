---
layout: post
title: "getLargerString.js"
categories: dev
tags: algo
---

#### 조건문 + boolean 알고리즘 문제

<br>

## problem

Write a function called '`getLargerString`'.

Given two strings,

'getLargerString' return the longer string.

\* <u>If the strings are the same length, return string1.</u>

<br>

## solution 01

```javascript
function getLargerString(string1, string2) {
   if (string1.length >= string2.length) {
      return string1;
   } else {
      return string2;
   }
}


getLargerString('Wassup', 'bro?');	// Wassup
getLargerString('Leo', 'Sam');		// Leo
```

<br>

## solution 02

```javascript
function getLargerString(string1, string2) {
   return string1.length >= string2.length ? string1 : string2;
}


getLargerString('Wassup', 'bro?');	// Wassup
getLargerString('Leo', 'Sam');		// Leo
```





