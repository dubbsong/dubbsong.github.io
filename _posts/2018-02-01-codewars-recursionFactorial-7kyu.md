---
layout: post
title: "recursionFactorial.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 재귀(recursion) 알고리즘 문제

<br>

## problem

You have to create the function '`recursionFactorial`'

that receives '`n`' and return '`n!`'.

<br>

You have to use `recursion`.

<br>

> `factorial`: 계승
>
> `5!` = 5 x 4 x 3 x 2 x 1

<br>

## solution

```javascript
function recursionFactorial(n) {
   return n > 1 ? n * recursionFactorial(n - 1) : 1;
}


recursionFactorial(0);	// 1
recursionFactorial(1);	// 1
recursionFactorial(2);	// 2
recursionFactorial(3);	// 6
recursionFactorial(9);	// 362880
```

