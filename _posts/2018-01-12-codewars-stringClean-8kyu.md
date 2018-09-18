---
layout: post
title: "stringClean.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 정규표현식(RegExp) + 반복문(for loop) + 조건문(if) 알고리즘 문제

<br>

## problem

Your program will take in a string

and clean out all numeric characters,

and return a string with spacing

and special characters `~#$%^&!@*():;"'.,?` all intact.

<br>

> `.includes()` method
>
> const numbers = [1, 2, 3, 4];
>
> numbers.includes(4);	// true

<br>

## solution 01

```javascript
function stringClean(string) {
   let result = '';
   const numbers = '0123456789';
   
   for (let i = 0; i < string.length; i++) {
      if (numbers.includes(string[i]) === false) {
         result += string[i];
      }
   }
   return result;
}


stringClean('E3at m2e2!!');	// Eat me!!
stringClean('Was4sup b4ro?');	// Wassup bro?
```

<br>

## solution 02

```javascript
function stringClean(string) {
   let result = '';
   const numbers = '0123456789';
   
   for (let i = 0; i < string.length; i++) {
      if (!numbers.includes(string[i])) {
         result += string[i];
      }
   }
   return result;
}


stringClean('E3at m2e2!!');	// Eat me!!
stringClean('Was4sup b4ro?');	// Wassup bro?
```

------

<br>

> `정규표현식 (Regular Expression)`
>
> `replace`: 일치하는 문자열을 찾는 String 메소드
>
> `\d`: 0~9까지의 숫자 반복 검색 = `[0-9]`
>
> `/g`: 전역 검색 (Global search). 첫 번째 일치 결과에서 멈추지 않고 전체 문자열에 대해 검색

<br>

## solution 03

```javascript
function stringClean(string) {
   return string.replace(/\d/g, '');
}


stringClean('E3at m2e2!!');	// Eat me!!
stringClean('Was4sup b4ro?');	// Wassup bro?
```

<br>

## solution 04

```javascript
function stringClean(string) {
   return string.replace(/[0-9]/g, '');
}


stringClean('E3at m2e2!!');	// Eat me!!
stringClean('Was4sup b4ro?');	// Wassup bro?
```

<br>

## solution 05

```javascript
const stringClean = string => string.replace(/\d/g, '');


stringClean('E3at m2e2!!');	// Eat me!!
stringClean('Was4sup b4ro?');	// Wassup bro?
```





