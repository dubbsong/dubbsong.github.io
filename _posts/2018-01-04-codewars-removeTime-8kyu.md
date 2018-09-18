---
layout: post
title: "removeTime.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function '`removeTime`'

that takes the Website date/time

in its original string format,

and returns the shortened format.

<br>

## solution 01

```javascript
function removeTime(longDate) {
   return longDate.split(',')[0];
}


removeTime('Fri Jan 1, 8pm');	// Fri Jan 1
removeTime('Sat Apr 4, 4pm');	// Sat Apr 4
```

<br>

## solution 02

```javascript
const removeTime = longDate => longDate.split(',')[0];


removeTime('Fri Jan 1, 8pm');	// Fri Jan 1
removeTime('Sat Apr 4, 4pm');	// Sat Apr 4
```

