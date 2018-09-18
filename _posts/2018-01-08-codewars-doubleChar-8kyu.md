---
layout: post
title: "doubleChar.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 문자열(string) 알고리즘 문제

<br>

## problem

Given a string, you have to return a string

in which each character is repeated once.

(case-sensitive)

<br>

## solution 01

```javascript
function doubleChar(string) {
   let result = '';
   
   for (let i = 0; i < string.length; i++) {
      result = result + string[i] + string[i];
   }
   return result;
}


doubleChar('aBcd');	// aaBBccdd
doubleChar('Ssup');	// SSssuupp
```

<br>

## solution 02

```javascript
const doubleChar = string => string.split('').map(a => a + a).join('');


doubleChar('aBcd');	// aaBBccdd
doubleChar('Ssup');	// SSssuupp
```

<br>

## solution 03

```javascript
const doubleChar = string => string.replace(/(.)/g, '$1$1');


doubleChar('aBcd');	// aaBBccdd
doubleChar('Ssup');	// SSssuupp
```

