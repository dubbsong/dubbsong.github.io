---
layout: post
title: "bouncerBlackList.js"
categories: dev
tags: algo
---

#### 조건문 + boolean 알고리즘 문제

<br>

## problem

Write a function called '`bouncerBlackList`'.

This guy named "<u>Leo</u>" keeps blacking out

at the bar that your function, bouncer.

<br>

## solution

```javascript
function bouncerBlackList(name, age) {
   if (name === 'Leo') {
      return `Go home Leo!`;
   }
   
   if (age >= 21) {
      return `Welcome, ${name}!`;
   } else {
      return `Go home, ${name}.`;
   }
}


bouncerBlackList('Leo', 26);	// Go home Leo!
bouncerBlackList('Sam', 19);	// Go home, Sam.
bouncerBlackList('Ralph', 34);	// Welcome, Ralph!
```

