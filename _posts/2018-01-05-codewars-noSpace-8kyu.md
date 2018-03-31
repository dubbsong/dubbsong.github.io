---
layout: post
title: "noSpace.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 문자열(string) 알고리즘 문제

<br>

## problem

Simple, remove the spaces from the string,

then return the resultant string.

<br>

## solution 01

```javascript
function noSpace(string) {
   return string.split(' ').join('');
}


noSpace('Wassup bro, how you doin?');	// Wassupbro,howyoudoin?
```

<br.

## solution 02

```javascript
const noSpace = string => string.split(' ').join('');


noSpace('Wassup bro, how you doin?');	// Wassupbro,howyoudoin?
```

<br>

## solution 03

```javascript
function noSpace(string) {
   return string.replace(/\s/g, '');
}


noSpace('Wassup bro, how you doin?');	// Wassupbro,howyoudoin?
```

