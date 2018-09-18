---
layout: post
title: "toFreud.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 정규표현식(RegExp) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

In this kata, the '`toFreud()`' function

will take a string as its argument,

and return a string with every word replaced

by the explanation to everything,

according to Freud.

<br>

Note that an empty string, or no arguments,

should result in the output being empty string('').

<br>

## solution 01

```javascript
function toFreud(string) {
   const splitted = string.split(' ').map(a => a = 'ssup');
   return string.length > 0 ? splitted.join(' ') : '';
}


toFreud('');			// ''
toFreud('something');		// ssup
toFreud('talk anything');	// ssup ssup
```

<br>

## solution 02

```javascript
function toFreud(string) {
   return string.replace(/[^ ]+/g, 'ssup');
}


toFreud('');			// ''
toFreud('something');		// ssup
toFreud('talk anything');	// ssup ssup
```

> `정규표현식 (Regular Expression)`
>
> `^`: 입력의 시작에 일치
>
> `+`: 1회 이상 연속으로 반복되는 문자에 일치
>
> `g`: 전역 검색 (Global search)

<br>

## solution 03

```javascript
const toFreud = string => string.replace(/[^ ]+/g, 'ssup');


toFreud('');			// ''
toFreud('something');		// ssup
toFreud('talk anything');	// ssup ssup
```

<br>

## solution 04

```javascript
const toFreud = string => string.replace(/\w+/g, 'ssup');


toFreud('');			// ''
toFreud('something');		// ssup
toFreud('talk anything');	// ssup ssup
```

> `정규표현식 (Regular Expression)`
>
> `\w`: 영숫자 문자에 일치 (= `[A-Za-z0-9_]`)

<br>

## solution 05

```javascript
const toFreud = string => string.replace(/\S+/g, 'ssup');


toFreud('');			// ''
toFreud('something');		// ssup
toFreud('talk anything');	// ssup ssup
```

> `정규표현식 (Regular Expression)`
>
> `\S`: 공백 문자가 아닌 하나의 문자에 일치

<br>

## solution 06

```javascript
function toFreud(string) {
   let result = [];
   const splitted = string.split(' ');
   
   if (string === '') {
      return '';
   } else {
      for (let i = 0; i < splitted.length; i++) {
         result.push('ssup');
      }
      return result.join(' ');
   }
   return result;
}


toFreud('');			// ''
toFreud('something');		// ssup
toFreud('talk anything');	// ssup ssup
```

