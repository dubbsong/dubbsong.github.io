---
layout: post
title: "repeatString.js"
categories: dev
tags: algo
---

#### 반복문(for loop) 알고리즘 문제

<br>

## problem

Repeating a String n Times:

Let's write a function called '`repeatString`'

that takes two parameters: a string,

which is the string to be repeated,

and n — a number representing

how many times the string should be repeated.

<br>

## solution 01

```javascript
function repeatString(string, n) {
   return string.repeat(n);
}


repeatString('ssup', 0);	// ''
repeatString('ssup', 1);	// ssup
repeatString('ssup', 2);	// ssupssup
repeatString('ssup', 3);	// ssupssupssup
```

<br>

## solution 02

```javascript
function repeatString(string, n) {
   let result = '';
   
   for (let i = 0; i < n; i++) {
      result += string;
   }
   return result;
}


repeatString('ssup', 0);	// ''
repeatString('ssup', 1);	// ssup
repeatString('ssup', 2);	// ssupssup
repeatString('ssup', 3);	// ssupssupssup
```

