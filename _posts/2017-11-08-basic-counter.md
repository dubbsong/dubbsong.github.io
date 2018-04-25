---
layout: post
title: "counter.js"
categories: dev
tags: algo
---

#### 변수 선언(variable) 알고리즘 문제

<br>

## problem

Write a function called '`counter`' that,

when invoked, always returns a number

that is one more than the previous invocation.

\* You'll need a variable for this(call it 'count').

<br>

## solution 01

```javascript
let count = 0;

function counter() {
   return count += 1;
}


counter();	// 1
counter();	// 2
counter();	// 3
```

> `대입 연산자 (Assignment Operators)`
>
> `+=`: `x += y` = `x = x + y`
>
> `-=`: `x -= y` = `x = x - y`
>
> `*=`: `x *= y` = `x = x * y`
>
> `/=`: `x /= y` = `x = x / y`

<br>

## solution 02

```javascript
let count = 0;

function counter() {
   return ++count;
}


counter();	// 1
counter();	// 2
counter();	// 3
```

> `++`: `x++` = `x = x + 1`

<br>