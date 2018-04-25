---
layout: post
title: "countChar.js"
categories: dev
tags: algo
---

#### 반복문(for loop) + 조건문(if) + 배열(array) 알고리즘 문제

<br>

## problem

Write a function '`countChar`'

that takes two arguments:

any string, and a character(string of one letter),

and returns the number of times

that the character occurs in the string.

Your function should ignore case.

<br>

## solution

```javascript
function countChar(string, char) {
   string = string.toLowerCase();
   let count = 0;
   
   for (let i = 0; i < string.length; i++) {
      if (string[i] === char) {
         count += 1;
      }
   }
   return count;
}


countChar('Ssup', 's');		// 2
countChar('ooOooui', 'o');	// 5
```

