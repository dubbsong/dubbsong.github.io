---
layout: post
title: "shortestWord.js"
categories: dev
tags: algo
---

#### 반복문(for loop) + 조건문(if) + 배열(array) 알고리즘 문제

<br>

## problem

Write a function '`shortestWord`'

that works like '`longestWord`',

but returns the shortest word instead.

<br>

## solution 01

```javascript
function shortestWord(string) {
   let splitted = string.split(' ');
   let shortest = splitted[0];
   
   for (let i = 0; i < splitted.length; i++) {
      if (shortest.length > splitted[i].length) {
         shortest = splitted[i];
      }
   }
   return shortest;
}


shortestWord('Wassup bro?');		// bro?
shortestWord('React JavaScript');	// React
```

<br>

## solution 02

```javascript
function shortestWord(string) {
   let splitted = string.split(' ');
   let shortest = splitted[0];
   
   for (let i of splitted) {
      if (shortest.length > i.length) {
         shortest = i;
      }
   }
   return shortest;
}


shortestWord('Wassup bro?');		// bro?
shortestWord('React JavaScript');	// React
```

