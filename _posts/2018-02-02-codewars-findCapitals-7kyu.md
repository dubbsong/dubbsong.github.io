---
layout: post
title: "findCapitals.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function

that takes a single string as arguments.

<br>

The function must return an ordered list

containing the indexes of all capital letters in the string.

<br>

## solution 01

```javascript
function findCapitals(string) {
   let result = [];
   
   for (let i = 0; i < string.length; i++) {
      if (string[i].toUpperCase() === string[i]) {
         result.push(i);
      }
   }
   return result;
}


findCapitals('CodeWars');	// [0, 4]
findCapitals('codeWaRs');	// [4, 6]
```

> `.toUpperCase()` 메소드
>
> 문자열에 있는 모든 영문자를 대문자로 변환한다.

<br>

## solution 02

```javascript
function findCapitals(string) {
   return string.match(/[A-Z]/g).map(a => string.indexOf(a));
}


findCapitals('CodeWars');	// [0, 4]
findCapitals('codeWaRs');	// [4, 6]
```

> 정규표현식 (RegExp)
>
> `match`: 정보를 가지고 있는 배열을 반환하거나 일치하지 않는 부분을 null로 반환한다.

<br>

> `.map()` 메소드
>
> 배열 내 모든 요소 각각에 대하여 제공된 함수(callback)를 호출하고,
>
> 그 결과를 모아서 새로운 배열을 반환한다.

<br>

> `.indexOf()` 메소드
>
> 일치하는 인덱스를 반환하고, 존재하지 않으면 -1을 반환한다.

<br>

