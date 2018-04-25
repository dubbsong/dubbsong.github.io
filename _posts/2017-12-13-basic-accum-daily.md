---
layout: post
title: "accum.js"
categories: dev
tags: algo
---

#### 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

This time no story, no theory.

<br>

The example below show you

how to write function '`accum`':

```javascript
// Examples:

accum('abcd');	// A-Bb-Ccc-Dddd
accum('AbcD');	// A-Bb-Ccc-Dddd
```

<br>

The parameter of accum is a string

which includes only letters

from '`a..z`' and '`A..Z`'.

<br>

## solution

```javascript
function accum(string) {
   let result = string[0].toUpperCase();
   
   for (let i = 1; i < string.length; i++) {
      result += '-';
      
      for (let j = 0; j <= i; j++) {
         result += j === 0
         	? string[i].toUpperCase()
         	: string[i].toLowerCase();
      }
   }
   return result;
}


accum('ssup');	// S-Ss-Uuu-Pppp
accum('SsuP');	// S-Ss-Uuu-Pppp
```

> `.toUpperCase()` 메소드
>
> 문자열에 있는 모든 알파벳을 대문자로 변환한 값을 반환한다.

<br>

> `.toLowerCase()` 메소드
>
> 문자열에 있는 모든 알파벳을 소문자로 변환한 값을 반환한다.

<br>

> `삼항 연산자 (ternary operator)`
>
> 조건식 `?` 조건이 true일 때 반환하는 값 `:` 조건이 false일 때 반환하는 값

<br>