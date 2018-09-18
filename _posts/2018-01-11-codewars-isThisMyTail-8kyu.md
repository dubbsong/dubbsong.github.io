---
layout: post
title: "isThisMyTail.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 불린(boolean) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

If the tail is right return true,

else return false.

<br>

## solution 01

```javascript
function isThisMyTail(body, tail) {
   if (body[body.length - 1] === tail) {
      return true;
   } else {
      return false;
   }
}


isThisMyTail('ssup', 's');	// false
isThisMyTail('ssup', 'p');	// true
```

<br>

## solution 02

```javascript
function isThisMyTail(body, tail) {
   const lastOfBody = body[body.length - 1];
   return lastOfBody === tail ? true : false;
}


isThisMyTail('ssup', 's');	// false
isThisMyTail('ssup', 'p');	// true
```

<br>

## solution 03

```javascript
function isThisMyTail(body, tail) {
   return body[body.length - 1] === tail;
}


isThisMyTail('ssup', 's');	// false
isThisMyTail('ssup', 'p');	// true
```

<br>

## solution 04

```javascript
const isThisMyTail = (body, tail) => body.slice(-1) === tail ? true : false;


isThisMyTail('ssup', 's');	// false
isThisMyTail('ssup', 'p');	// true
```

<br>

## solution 05

```javascript
const isThisMyTail = (body, tail) => body.charAt(body.length - 1) === tail ? true : false;


isThisMyTail('ssup', 's');	// false
isThisMyTail('ssup', 'p');	// true
```

