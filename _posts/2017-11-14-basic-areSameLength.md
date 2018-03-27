---
layout: post
title: "areSameLength.js"
categories: dev
tags: algo
---

#### 조건문(if) + 불린(boolean) 알고리즘 문제

<br>

## problem

Write a function called '`areSameLength`'.

Given two strings,

'areSameLength' returns true

if they are of the same length,

and false otherwise.

<br>

## solution 01

```javascript
function areSameLength(string1, string2) {
   if (string1.length === string2.length) {
      return true;
   } else {
      return false;
   }
}


areSameLength('Wassup', 'bro?');	// false
areSameLength('Sam', 'Leo');		// true
```

<br>

## solution 02

```javascript
function areSameLength(string1, string2) {
   return string1.length === string2.length ? true : false;
}


areSameLength('Wassup', 'bro?');	// false
areSameLength('Sam', 'Leo');		// true
```



