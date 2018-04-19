---
layout: post
title: "removeVowels.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 정규표현식(RegExp) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Create a function called '`removeVowels`'

to remove all the lowercase vowels

in a given string.

<br>

Don't worry about uppercase vowels.

<br>

## solution 01

```javascript
function removeVowels(string) {
   let result = [];
   
   for (let i = 0; i < string.length; i++) {
      if (string[i] === 'a' ||
         string[i] === 'e' ||
         string[i] === 'i' ||
         string[i] === 'o' ||
          string[i] === 'u') {
         string[i] = '';
      } else {
         result.push(string[i]);
      }
   }
   return result.join('');
}


removeVowels('Wassup bro?');	// Wssp br?
```

<br>

## solution 02

```javascript
function removeVowels(string) {
   let vowels = 'aeiou';
   let result = '';
   
   for (let i = 0; i < string.length; i++) {
      if (vowels.indexOf(string[i]) === -1) {
         result += string[i];
      }
   }
   return result;
}


removeVowels('Wassup bro?');	// Wssp br?
```

<br>

## solution 03

```javascript
function removeVowels(string) {
   return string.replace(/[aeiou]/g, '');
}


removeVowels('Wassup bro?');	// Wssp br?
```

> `정규표현식 (RegExp)`
>
> `g`: 전역 검색 (Global search)

<br>

## solution 04

```javascript
const removeVowels = string => string.replace(/[aeiou]/g, '');


removeVowels('Wassup bro?');	// Wssp br?
```

<br>

## solution 05

```javascript
function removeVowels(string) {
   return string.replace(/[aeiou]/gi, '');
}


removeVowels('Wassup bro?');	// Wssp br?
```

> `정규표현식 (RegExp)`
>
> `g`: 전역 검색 (Global search)
>
> `i`: 대소문자 구별 없이 검색 (Case-insensitive search)

<br>

## solution 06

```javascript
function removeVowels(string) {
   return string.replace(/[aeiou]+/g, '');
}


removeVowels('Wassup bro?');	// Wssp br?
```

> `정규표현식 (RegExp)`
>
> `g`: 전역 검색 (Global search)
>
> `+`: 1회 이상 연속으로 반복되는 문자에 일치

<br>