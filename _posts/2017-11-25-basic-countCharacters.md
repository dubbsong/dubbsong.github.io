---
layout: post
title: "countCharacters.js"
categories: dev
tags: algo
---

#### 반복문(for loop) + 조건문(if) + 객체(object) 알고리즘 문제

<br>

## problem

Write a function '`countCharacters`' that

when given a string as an argument,

returns an object containing counts of the occurrences

of each character in the string.

<br>

You will want to make use of the string method, '`split`'.

Try 'hello'.split('') in the console to see how it works.

<br>

## solution 01

```javascript
function countCharacters(string) {
   let obj = {};
   let splitted = string.split('');
   
   for (let i = 0; i < splitted.length; i++) {
      if (obj.hasOwnProperty(splitted[i])) {
         obj[splitted[i]]++;
      } else {
         obj[splitted[i]] = 1;
      }
   }
   return obj;
}


countCharacters('ssup');	// { s: 2, u: 1, p: 1 }
countCharacters('Ssup');	// { S: 1, s: 1, u: 1, p: 1 }
```

<br>

## solution 02

```javascript
function countCharacters(string) {
   let obj = {};
   let splitted = string.split('');
   
   for (let i of splitted) {
      if (obj.hasOwnProperty(i)) {
         obj[i]++;
      } else {
         obj[i] = 1;
      }
   }
   return obj;
}


countCharacters('ssup');	// { s: 2, u: 1, p: 1 }
countCharacters('Ssup');	// { S: 1, s: 1, u: 1, p: 1 }
```

<br>

## solution 03

```javascript
function countCharacters(string) {
   let obj = {};
   let splitted = string.split('');
   
   for (let i of splitted) {
      obj.hasOwnProperty(i) ? obj[i]++ : obj[i] = 1;
   }
   return obj;
}


countCharacters('ssup');	// { s: 2, u: 1, p: 1 }
countCharacters('Ssup');	// { S: 1, s: 1, u: 1, p: 1 }
```

