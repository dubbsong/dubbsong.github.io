---
layout: post
title: "addLength.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Your task is to write a function

that takes a string and returns an Array/list

with the length of each word added to each element.

<br>

String will have at least one element,

words will always be separated by a space.

<br>

## solution 01

```javascript
function addLength(string) {
   let splitted = string.split(' ');
   
   for (let i = 0; i < splitted.length; i++) {
      splitted[i] = splitted[i] + ' ' + splitted[i].length;
   }
   return splitted;
}


addLength('Wassup bro?');	// ['Wassup 6', 'bro? 4']
```

<br>

## solution 02

```javascript
function addLength(string) {
   let splitted = string.split(' ');
   let result = [];
   
   for (let i = 0; i < splitted.length; i++) {
      result.push(splitted[i] + ' ' + splitted[i].length);
   }
   return result;
}


addLength('Wassup bro?');	// ['Wassup 6', 'bro? 4']
```

<br>

## solution 03

```javascript
function addLength(string) {
   return string.split(' ').map(a => `${a} ${a.length}`);
}


addLength('Wassup bro?');	// ['Wassup 6', 'bro? 4']
```

<br>

## solution 04

```javascript
const addLength = string => string.split(' ').map(a => `${a} ${a.length}`);


addLength('Wassup bro?');	// ['Wassup 6', 'bro? 4']
```

