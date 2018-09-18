---
layout: post
title: "addBinary.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Implement a function

that adds two numbers together

and returns their sum in binary.

<br>

The conversion can be done before,

or after the addition.

<br>

The binary number returned should be a string.

<br>

## solution

```javascript
function addBinary(a, b) {
   return (a + b).toString(2);
}


addBinary(1, 2);	// 11
addBinary(30, 33);	// 111111
```

> `.toString()` 메소드
>
> 인자에 해당하는 진수를 반환한다.

<br>