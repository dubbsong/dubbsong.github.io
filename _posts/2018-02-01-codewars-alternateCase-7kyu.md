---
layout: post
title: "alternateCase.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write function '`alternateCase`'

which switch every letter in string

from upper to lower and from lower to upper.

<br>

## solution 01

```javascript
function alternateCase(string) {
   let result = '';
   
   for (let i = 0; i < string.length; i++) {
      if (string[i] === string[i].toUpperCase()) {
         result += string[i].toLowerCase();
      } else if (string[i] === string[i].toLowerCase()) {
         result += string[i].toUpperCase();
      } else {
         result += string[i];
      }
   }
   return result;
}


alternateCase('abcd');	// ABCD
alternateCase('ssup');	// SSUP
```

<br>

## solution 02

```javascript
function alternateCase(string) {
   return string.split('').map(a => {
      return a === a.toUpperCase() ? a.toLowerCase() : a.toUpperCase()
   }).join('');
}


alternateCase('abcd');	// ABCD
alternateCase('ssup');	// SSUP
```

> `.split()` 메소드
>
> 문자열을 부분 문자열로 분할해서, 배열로 반환한다.

<br>

> `.map()` 메소드
>
> 배열 내 모든 요소 각각에 대하여
>
> 제공된 함수(callback)를 호출하고,
>
> 그 결과를 모아서 새로운 배열을 반환한다.

<br>

> `.join()` 메소드
>
> 배열의 모든 요소를 연결해 하나의 문자열로 만들고, 문자열을 반환한다.

<br>

## solution 03

```javascript
function alternateCase(string) {
   return [...string].map(a => {
      return a === a.toUpperCase() ? a.toLowerCase() : a.toUpperCase()
   }).join('');
}


alternateCase('abcd');	// ABCD
alternateCase('ssup');	// SSUP
```

<br>

## solution 04

```javascript
function alternateCase(string) {
   return string.replace(/([a-z])|([A-Z])/g, (a, b) => {
      return b ? a.toUpperCase() : a.toLowerCase()
   });
}


alternateCase('abcd');	// ABCD
alternateCase('ssup');	// SSUP
```

> 정규표현식 (RegExp)
>
> `replace`: 일치하는 문자열을 replacement로 대체한다.

<br>