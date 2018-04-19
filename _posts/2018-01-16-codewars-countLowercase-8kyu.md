---
layout: post
title: "countLowercase.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 정규표현식(RegExp) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Your task is simply

to count the total number of lowercase letters

in a string.

<br>

> `정규표현식 (Regular Expression)`
>
> ^: 입력의 시작에 일치
>
> .match(): 일치하는 문자열을 찾는 String 메소드 (배열을 반환)
>

<br>

## solution 01

```javascript
function countLowercase(string) {
   return string.replace(/[^a-z]/g, '').length;
}


countLowercase('');		// 0
countLowercase('abc');		// 3
countLowercase('abcABC');	// 3
countLowercase('!@#$ssup%^&*');	// 4
```

<br>

## solution 02

```javascript
const countLowercase = string => string.replace(/[^a-z]/g, '').length;


countLowercase('');		// 0
countLowercase('abc');		// 3
countLowercase('abcABC');	// 3
countLowercase('!@#$ssup%^&*');	// 4
```

<br>

## solution 03

```javascript
function countLowercase(string) {
   return (string.match(/[a-z]/g) || []).length;
}


countLowercase('');		// 0
countLowercase('abc');		// 3
countLowercase('abcABC');	// 3
countLowercase('!@#$ssup%^&*');	// 4
```

<br>

## solution 04

```javascript
const countLowercase = string => (string.match(/[a-z]/g) || []).length;


countLowercase('');		// 0
countLowercase('abc');		// 3
countLowercase('abcABC');	// 3
countLowercase('!@#$ssup%^&*');	// 4
```

