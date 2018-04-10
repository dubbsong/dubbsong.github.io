---
layout: post
title: "reverseWord.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 문자열(string) 알고리즘 문제

<br>

## problem

You need to write a function

that reverses the words in a given string.

A word can also fit an empty string.

<br>

## solution 01

```javascript
function reverseWord(string) {
   return string.split(' ').reverse().join(' ');
}


reverseWord('Codewars');	// Codewars
reverseWord('Wassup bro?');	// bro? Wassup
```

<br>

## solution 02

```javascript
const reverseWord = string => string.split(' ').reverse().join(' ');


reverseWord('Codewars');	// Codewars
reverseWord('Wassup bro?');	// bro? Wassup
```



