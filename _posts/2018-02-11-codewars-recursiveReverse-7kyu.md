---
layout: post
title: "recursiveReverse.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 재귀(recursion) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Do you know how to write a recursive function?

<br>

> Definition:
>
> Recursive function is a function
>
> that calls itself during its execution.

<br>

Your objective is

to complete a recursive function '`recursiveReverse()`'

that receives '`string`' as String

and returns the same string in reverse order.

<br>

> Rules:
>
> Reverse function should be executed only N times.
>
> Helper functions are not allowed.
>
> Changing the signature of the function is not allowed.

<br>

## solution 01

```javascript
function recursiveReverse(string) {
   return string.length > 1
   	? recursiveReverse(string.slice(1)) + string[0]
   	: string;
}


recursiveReverse('a');	// a
recursiveReverse('ab');	// ba
recursiveReverse('ssup');	// puss
```

> `.slice()` 메소드
>
> 문자열의 일부를 추출하면서 새로운 문자열을 반환한다.

<br>

## solution 02

```javascript
function recursiveReverse(string) {
   return string.length > 1
   	? string.slice(-1) + recursiveReverse(string.slice(0, -1))
   	: string;
}


recursiveReverse('a');	// a
recursiveReverse('ab');	// ba
recursiveReverse('ssup');	// puss
```

