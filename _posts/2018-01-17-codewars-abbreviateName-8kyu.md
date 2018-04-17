---
layout: post
title: "abbreviateName.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 정규표현식(RegExp) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function

to convert a name into initials.

<br>

The output should be two capital letters

with a dot seperating them.

<br>

## solution 01

```javascript
function abbreviateName(name) {
   let splitted = name.split(' ');
   return splitted[0][0] + "." + splitted[1][0].toUpperCase();
}


abbreviateName('Sam Azor');		// S.A
abbreviateName('Sam azor');		// S.A
abbreviateName('Ralph Donovan');	// R.D
```

> `.toUpperCase() 메소드`
>
> 문자열에 있는 모든 영문자를 대문자로 변환한다.

<br>

## solution 02

```javascript
function abbreviateName(name) {
   let splitted = name.split(' ');
   return `${splitted[0][0]}.${splitted[1][0]}`.toUpperCase();
}


abbreviateName('Sam Azor');		// S.A
abbreviateName('Sam azor');		// S.A
abbreviateName('Ralph Donovan');	// R.D
```

<br>

## solution 03

```javascript
const abbreviateName = name => `${(name = name.toUpperCase().split(' '))[0][0]}.${name[1][0]}`;


abbreviateName('Sam Azor');		// S.A
abbreviateName('Sam azor');		// S.A
abbreviateName('Ralph Donovan');	// R.D
```

<br>

## solution 04

```javascript
function abbreviateName(name) {
   return name.match(/\b\w/g).join('.').toUpperCase();
}


abbreviateName('Sam Azor');		// S.A
abbreviateName('Sam azor');		// S.A
abbreviateName('Ralph Donovan');	// R.D
```

> `정규표현식 (RegExp)`
>
> `match`: 일치하는 문자열을 찾는 String 메소드. 배열이나 null을 반환한다.
>
> `\b`: 단어의 경계와 일치한다.
>
> `\w`: 영숫자 문자에 일치한다. (= `[A-Za-z0-9_]`)

<br>