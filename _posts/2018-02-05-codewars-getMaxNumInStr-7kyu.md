---
layout: post
title: "getMaxNumInStr.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

You will be given a string

that has lowercase letters and numbers.

<br>

Your task is to compare the number groupings

and return the largest number.

<br>

## solution 01

```javascript
function getMaxNumInStr(string) {
   return Math.max(...string.match(/\d+/g));
}


getMaxNumInStr('4ssup12bro?');	// 12
getMaxNumInStr('4how8areyou');	// 8
```

> 정규표현식 (RegExp)
>
> `match`: 정보를 가지고 있는 배열을 반환하거나, 일치하지 않는 부분을 null로 반환한다.
>
> `\d`: 숫자 문자에 일치한다. (= `[0-9]`)
>
> `+`: 1회 이상 연속으로 반복되는 앞선 문자에 일치한다.
>
> `g`: 전역 검색 (Global search)

<br>

## solution 02

```javascript
function getMaxNumInStr(string) {
   string = string.match(/\d+/g);
   string.sort((a, b) => b - a);
   return Number(string[0]);
}


getMaxNumInStr('4ssup12bro?');	// 12
getMaxNumInStr('4how8areyou');	// 8
```

> `.sort()` 메소드
>
> 배열의 요소를 적절한 위치에 정렬하고, 배열을 반환한다.

<br>

## solution 03

```javascript
function getMaxNumInStr(string) {
   string = string.match(/\d+/g);
   string.sort((a, b) => a - b);
   return Number(string[string.length - 1]);
}


getMaxNumInStr('4ssup12bro?');	// 12
getMaxNumInStr('4how8areyou');	// 8
```

<br>

## solution 04

```javascript
function getMaxNumInStr(string) {
   return Number(string.match(/\d+/g).sort((a, b) => a - b).pop());
}


getMaxNumInStr('4ssup12bro?');	// 12
getMaxNumInStr('4how8areyou');	// 8
```

> `.pop()` 메소드
>
> 배열에서 마지막 요소를 제거하고, 제거된 요소를 반환한다.

<br>

## solution 05

```javascript
function getMaxNumInStr(string) {
   string = string.split(/[a-z]/g);
   console.log(string);
   let result = 0;
   
   for (let i = 0; i < string.length; i++) {
      if (+string[i] > result) {
         result = +string[i];
      }
   }
   return result;
}


getMaxNumInStr('4ssup12bro?');
// ['4', '', '', '', '12', '', '', '?']
// 12
getMaxNumInStr('4how8areyou');
// ['4', '', '', '8', '', '', '', '', '', '']
// 8
```

> `.split()` 메소드
>
> 문자열을 부분 문자열로 분할해서 배열로 반환한다.

<br>