---
layout: post
title: "isPasswordLongEnough.js"
categories: dev
tags: algo
---

#### 조건문(if) + 불린(boolean) 알고리즘 문제

<br>

Write a function called '`isPasswordLongEnough`'.

Given a string and a integer,

in this case a password and a minimum required length,

'isPasswordLongEnough' return

whether the inputted password is long enough.

<br>

## solution 01

```javascript
function isPasswordLongEnough(password, minimumLength) {
   if (password.length >= minimumLength) {
      return true;
   } else {
      return false;
   }
}


isPasswordLongEnough('qlqjs12', 8); 	// false
isPasswordLongEnough('votmdnjem', 8);	// true
```

<br>

## solution 02

```javascript
function isPasswordLongEnough(password, minimumLength) {
   return password.length >= minimumLength ? true : false;
}


isPasswordLongEnough('qlqjs12', 8); 	// false
isPasswordLongEnough('votmdnjem', 8);	// true
```

<br>

## solution 03

```javascript
const isPasswordLongEnough = (password, minimumLength) => password.length >= minimumLength ? true : false;


isPasswordLongEnough('qlqjs12', 8); 	// false
isPasswordLongEnough('votmdnjem', 8);	// true
```

