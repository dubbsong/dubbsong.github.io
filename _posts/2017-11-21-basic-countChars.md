---
layout: post
title: "countChars.js"
categories: dev
tags: algo
---

#### 조건문(if) + 반복문(for loop) 알고리즘 문제

<br>

## problem

Write a function called '`countChars`'

that accepts two parameters:

a string and a character.

<br>

## solution

```javascript
function countChars(string, character) {
   let count = 0;
   
   for (let i = 0; i < string.length; i++) {
      if (string[i] === character) {
         count += 1;
      }
   }
   return count;
}


countChars('Wassup', 'W');	// 1 (대문자 W)
countChars('Wassup', 's');	// 2
countChars('Wassup', 'w');	// 0 (소문자 w)
```



