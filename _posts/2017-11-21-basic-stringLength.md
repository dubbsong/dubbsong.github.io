---
layout: post
title: "stringLength.js"
categories: dev
tags: algo
---

#### 반복문(for loop) 알고리즘 문제

<br>

## problem

Your task is to write a function called '`stringLength`'

that accepts a string as a parameter

and computes the length of that string.

<br>

## solution 01

```javascript
function stringLength(string) {
   let result = 0;
   
   for (let i = 0; i < string.length; i++) {
      result += 1;
   }
   return result;
}


stringLength('Wassup bro?');	// 11
stringLength('How are you?');	// 12
```

<br>

## solution 02

```javascript
function stringLength(string) {
   let result = 0;
   
   for (let i in string) {
      result++;
   }
   return result;
}


stringLength('Wassup bro?');	// 11
stringLength('How are you?');	// 12
```

