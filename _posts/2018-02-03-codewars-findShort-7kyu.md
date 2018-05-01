---
layout: post
title: "findShort.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Simple, given a string of words,

return the length of the shortest word(s).

<br>

String will never be empty

and you do not need to account

for different data types.

<br>

## solution 01

```javascript
function findShort(string) {
   const splitted = string.split(' ');
   let min = splitted[0];
   
   for (let i = 0; i < splitted.length; i++) {
      if (min.length > splitted[i].length) {
         min = splitted[i];
      }
   }
   return min.length;
}


findShort('Wassup bro? How are you?');	// 3
```

<br>

## solution 02

```javascript
function findShort(string) {
   return Math.min(...string.split(' ').map(a => a.length));
}


findShort('Wassup bro? How are you?');	// 3
```

> `.map()` 메소드
>
> 배열 내 모든 요소 각각에 대하여
>
> 제공된 함수(callback)를 호출하고,
>
> 그 결과를 모아서 새로운 배열을 반환한다.

<br>



