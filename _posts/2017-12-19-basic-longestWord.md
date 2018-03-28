---
layout: post
title: "longestWord.js"
categories: dev
tags: algo
---

#### 반복문(for loop) + 조건문(if) + 배열(array) 알고리즘 문제

<br>

## problem

Write a function '`longestWord`'

that takes a string as an argument

and returns the longest word.

Implement using the method String.prototype.split().

<br>

> var string = 'How are you?';
>
> var result = string.split(' ');
>
> console.log(result);
>
> // ['How', 'are', 'you?']

<br>

## solution 01

```javascript
function longestWord(string) {
   let splitted = string.split(' ');
   let longest = splitted[0];
   
   for (let i = 0; i < splitted.length; i++) {
      if (longest.length < splitted[i].length) {
         longest = splitted[i];
      }
   }
   return longest;
}


longestWord('Wassup bro?');		// Wassup
longestWord('React JavaScript');	// JavaScript
```

<br>

## solution 02

```javascript
function longestWord(string) {
   let splitted = string.split(' ');
   let longest = splitted[0];
   
   for (let i of splitted) {
      if (longest.length < i.length) {
         longest = i;
      }
   }
   return longest;
}


longestWord('Wassup bro?');		// Wassup
longestWord('React JavaScript');	// JavaScript
```



