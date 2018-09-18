---
layout: post
title: "countChar.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

The goal of this kata is

to write a function that takes two inputs:

a string and a character.

<br>

The function will count the number of times

that character appears in the string.

<br>

The count is case insensitive.

<br>

## solution 01

```javascript
function countChar(string, char) {
   string = string.toLowerCase();
   char = char.toLowerCase();
   let result = 0;
   
   for (let i = 0; i < string.length; i++) {
      if (string[i] === char) {
         result += 1;
      }
   }
   return result;
}


countChar('WASSUP', 's');	// 2
```

> `.toLowerCase()` 메소드
>
> 모든 영문자를 소문자로 변경한다.

<br>

## solution 02

```javascript
function countChar(string, char) {
   string = string.toLowerCase();
   char = char.toLowerCase();
   
   return string.split('').filter(a => a === char).length;
}


countChar('WASSUP', 's');	// 2
```

> `.split()` 메소드
>
> 문자열을 부분 문자열로 분할해서, 배열로 반환한다.

<br>

> `.filter()` 메소드
>
> 테스트를 통과한 요소로 채워진 새로운 배열을 반환한다.

<br>

## solution 03

```javascript
function countChar(string, char) {
   return (string.match(new RegExp(char, 'gi')) || []).length;
}


countChar('WASSUP', 's');	// 2
```



