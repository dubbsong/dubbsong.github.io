---
layout: post
title: "toLeetSpeak.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Your task is to write a function '`toLeetSpeak`'

that converts a regular english sentence to Leetspeak.

<br>

Consider only uppercase letters and spaces.

<br>

> `leetspeak`: (숫자나 부호를 조합해서 만든) 인터넷 속어

<br>

## solution 01

```javascript
const leetSpeak = {
  A: '@', B: '8', C: '(', E: '3',
  G: '6', H: '#', I: '!', L: '1',
  O: '0', S: '$', T: '7', Z: '2'
}


function toLeetSpeak(string) {
   return string.replace(/[ABCEGHILOSTZ]/g, a => leetSpeak[a]);
}


toLeetSpeak('HELLO WORLD');	// #3110 W0R1D
toLeetSpeak('WASSUP BRO?');	// W@$$UP 8R0?
```

> 정규표현식 (RegExp)
>
> `replace`: 일치하는 문자열을 replacement로 대체한다.
>
> `g`: 전역 검색 (Global search)

<br>

## solution 02

```javascript
const leetSpeak = {
  A: '@', B: '8', C: '(', E: '3',
  G: '6', H: '#', I: '!', L: '1',
  O: '0', S: '$', T: '7', Z: '2'
}


function toLeetSpeak(string) {
   return string.split('').map(a => leetSpeak[a] || a).join('');
}


toLeetSpeak('HELLO WORLD');	// #3110 W0R1D
toLeetSpeak('WASSUP BRO?');	// W@$$UP 8R0?
```

> `.split()` 메소드
>
> 문자열을 부분 문자열로 분할해서 배열로 반환한다.

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
const leetSpeak = {
  A: '@', B: '8', C: '(', D: 'D',
  E: '3', F: 'F', G: '6', H: '#',
  I: '!', J: 'J', K: 'K', L: '1',
  M: 'M', N: 'N', O: '0', P: 'P',
  Q: 'Q', R: 'R', S: '$', T: '7',
  U: 'U', V: 'V', W: 'W', X: 'X',
  Y: 'Y', Z: '2', ' ': ' ', '?': '?'
}


function toLeetSpeak(string) {
   string = string.toUpperCase().split('');
   
   for (let i in string) {
      string[i] = leetSpeak[string[i]];
   }
   return string.join('');
}


toLeetSpeak('HELLO WORLD');	// #3110 W0R1D
toLeetSpeak('WASSUP BRO?');	// W@$$UP 8R0?
```

> `.toUpperCase()` 메소드
>
> 문자열에 있는 모든 영문자를 대문자로 변환한다.

<br>