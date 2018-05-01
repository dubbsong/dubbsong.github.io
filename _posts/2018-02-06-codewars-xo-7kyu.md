---
layout: post
title: "xo.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Check to see

if a string has the same

amount of '`x`'s and '`o`'s.

<br>

The method must return a boolean

and be case insensitive.

<br>

The string can contain any char.

<br>

## solution 01

```javascript
function xo(string) {
   string = string.toLowerCase();
   let result = 0;
   
   for (let i = 0; i < string.length; i++) {
      if (string[i] === 'x') {
         result += 1;
      }
      
      if (string[i] === 'o') {
         result -= 1;
      }
   }
   return result === 0;
}

xo('xo');	// true
xo('xxo');	// false
xo('xoo');	// false
xo('xXoo');	// true
```

<br>

## solution 02

```javascript
function xo(string) {
   let x = string.replace(/x/gi, '');
   let o = string.replace(/o/gi, '');
   return x.length === o.length;
}

xo('xo');	// true
xo('xxo');	// false
xo('xoo');	// false
xo('xXoo');	// true
```

> 정규표현식 (Regular Expression)
>
> `replace`: 일치하는 문자열을 replacement로 대체한다.
>
> `g`: 전역 검색 (Global search)
>
> `i`: 대소문자 구별없이 검색 (Case-insensitive search)

<br>

## solution 03

```javascript
function xo(string) {
   let x = string.match(/x/gi);
   let o = string.match(/o/gi);
   return (x && x.length) === (o && o.length);
}

xo('xo');	// true
xo('xxo');	// false
xo('xoo');	// false
xo('xXoo');	// true
```

> 정규표현식 (RegExp)
>
> `match`: 정보를 가지고 있는 배열을 반환하거나 일치하지 않는 부분을 null로 반환한다.

<br>