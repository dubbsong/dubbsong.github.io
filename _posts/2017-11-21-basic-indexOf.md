---
layout: post
title: "indexOf.js"
categories: dev
tags: algo
---

#### 조건문(if) + 반복문(for loop) 알고리즘 문제

<br>

## problem

Implement a function called '`indexOf`'

that accepts two parameters:

a string and a character,

and returns the first index of character

in the string.

<br>

## solution 01

```javascript
function indexOf(string, character) {
   return string.indexOf(character);
}


indexOf('Wassup bro?', 'b');	// 7
indexOf('How are you?', 'a');	// 4
```

> `.indexOf()` 메소드
>
> 문자열에서 지정된 요소와 일치하는 첫 번째 요소의 인덱스를 반환한다.
>
> 일치하는 값이 없으면 `-1`을 반환한다.

<br>

## solution 02

```javascript
function indexOf(string, character) {
   let count = 0;
   
   for (let i = 0; i < string.length; i++) {
      if (string[i] === character) {
         count += i;
      }
   }
   return count;
}


indexOf('Wassup bro?', 'b');	// 7
indexOf('How are you?', 'a');	// 4
```

