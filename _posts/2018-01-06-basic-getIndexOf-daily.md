---
layout: post
title: "getIndexOf.js"
categories: dev
tags: algo
---

#### 문자열(string) + 조건문(if) + 반복문(for loop) 활용 알고리즘 문제

<br>

## problem

Write a function called '`getIndexOf`'.

<br>

Given a character and a string,

'getIndexOf' returns the first position

of the given character in the given string.

<br>

> Notes:
>
> Strings are zero indexed, meaning the fisrt character
>
> in a string is at position 0.

<br>

When a string contains more than

one occurrence of a character,

it should return the index of its first occurrence.

<br>

If the character does not exist in the string,

it should return '`-1`'.

<br>

Do not use the native '`indexOf`' function

in your implementation.

<br>

## solution

```javascript
function getIndexOf(string, char) {
   for (let i = 0; i < string.length; i++) {
      if (char === string[i]) {
         return i;
      }
   }
   return -1;
}


getIndexOf('ssup', 'u');	// 2
getIndexOf('ssup', 'd');	// -1
```

<br>

## solution (indexOf 메소드 사용)

```javascript
function getIndexOf(string, char) {
   return string.indexOf(char);
}


getIndexOf('ssup', 'u');	// 2
getIndexOf('ssup', 'd');	// -1
```

> `.indexOf` 메소드
>
> 배열에서 지정된 요소(element)를 찾을 수 있는 첫 번째 인덱스를 반환한다.
>
> 존재하지 않으면 -1을 반환한다.

<br>