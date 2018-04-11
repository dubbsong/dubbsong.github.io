---
layout: post
title: "validateUser.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 정규표현식(RegExp) 알고리즘 문제

<br>

## problem

Write a simple Reg Exp

to validate a '`username`'.

<br>

Allowed characters are:

`lowercase letters`, `numbers`, `underscore`

<br>

Length should be

`between 4 and 16` characters.

<br>

> `정규표현식 (Regular Expression)`
>
> ^: 입력의 시작에 일치
>
> $: 입력의 끝에 일치
>
> \d: 숫자 문자에 일치
>
> {n}: 앞 문자가 n번 나타날 경우 일치
>
> {n, m}: 앞 문자가 최소 n개, 최대 m개 나타날 경우 일치 (n <= m)
>
> .test(): 일치하는 문자열을 검사하는 RegExp 메소드 (true나 false를 반환)

<br>

## solution 01

```javascript
function validateUser(username) {
   return /^[a-z0-9_]{4,16}$/.test(username);
}


validateUser('a');		// false
validateUser('dubbsong');	// true
validateUser('Dubbsong');	// false
validateUser('code wars');	// false
validateUser('code_wars');	// true
```

<br>

## solution 02

```javascript
function validateUser(username) {
   return /^[a-z_0-9]{4,16}$/.test(username);
}


validateUser('a');		// false
validateUser('dubbsong');	// true
validateUser('Dubbsong');	// false
validateUser('code wars');	// false
validateUser('code_wars');	// true
```

<br>

## solution 03

```javascript
function validateUser(username) {
   return /^[a-z\d_]{4,16}$/.test(username);
}


validateUser('a');		// false
validateUser('dubbsong');	// true
validateUser('Dubbsong');	// false
validateUser('code wars');	// false
validateUser('code_wars');	// true
```

<br>

## solution 04

```javascript
const validateUser = username => /^[a-z0-9_]{4,16}$/.test(username);


validateUser('a');		// false
validateUser('dubbsong');	// true
validateUser('Dubbsong');	// false
validateUser('code wars');	// false
validateUser('code_wars');	// true
```

