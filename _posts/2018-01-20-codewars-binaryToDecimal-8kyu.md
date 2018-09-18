---
layout: post
title: "binaryToDecimal.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Complete the function

which converts a binary number (given as a string)

to a decimal number.

<br>

## solution 01

```javascript
function binaryToDecimal(binary) {
   return parseInt(binary, 2);
}


binaryToDecimal('0', 2);	// 0
binaryToDecimal('1', 2);	// 1
binaryToDecimal('10', 2);	// 2
binaryToDecimal('11', 2);	// 3
binaryToDecimal('100', 2);	// 4
binaryToDecimal('101', 2);	// 5
binaryToDecimal('110', 2);	// 6
binaryToDecimal('111', 2);	// 7
binaryToDecimal('1000', 2);	// 8
binaryToDecimal('1001', 2);	// 9
binaryToDecimal('1010', 2);	// 10
```

<br>

## solution 02

```javascript
const binaryToDecimal = binary => parseInt(binary, 2);


binaryToDecimal('0', 2);	// 0
binaryToDecimal('1', 2);	// 1
binaryToDecimal('10', 2);	// 2
binaryToDecimal('11', 2);	// 3
binaryToDecimal('100', 2);	// 4
binaryToDecimal('101', 2);	// 5
binaryToDecimal('110', 2);	// 6
binaryToDecimal('111', 2);	// 7
binaryToDecimal('1000', 2);	// 8
binaryToDecimal('1001', 2);	// 9
binaryToDecimal('1010', 2);	// 10
```

