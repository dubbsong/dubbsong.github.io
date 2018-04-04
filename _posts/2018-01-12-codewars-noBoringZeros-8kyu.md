---
layout: post
title: "noBoringZeros.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(while) + 정규표현식(RegExp) 알고리즘 문제

<br>

## problem

Numbers ending with zeros are boring.

Get rid of them.

Only the ending ones.

<br>

> `정규표현식 (RegExp)`
>
> $: 특정 단어로 끝나는지 검사
>
> *: 0회 이상 반복되는 문자열 찾기
>
> +: 1회 이상 반복되는 문자열 찾기
>
> g: 전역 검색

<br>

## solution 01

```javascript
function noBoringZeros(number) {
   while (number % 10 === 0 && number !== 0) {
      number /= 10;
   }
   return number;
}


noBoringZeros(0);	// 0
noBoringZeros(9900);	// 99
noBoringZeros(900900);	// 9009
```

<br>

## solution 02

```javascript
function noBoringZeros(number) {
   return +`${number}`.replace(/0+$/g, '');
}


noBoringZeros(0);	// 0
noBoringZeros(9900);	// 99
noBoringZeros(900900);	// 9009
```

<br>

## solution 03

```javascript
const noBoringZeros = number => +`${number}`.replace(/0+$/g, '');


noBoringZeros(0);	// 0
noBoringZeros(9900);	// 99
noBoringZeros(900900);	// 9009
```

