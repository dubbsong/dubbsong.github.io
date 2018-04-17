---
layout: post
title: "removeQuestionMarks3.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 정규표현식(RegExp) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Remove a question mark from the end of string.

<br>

## solution 01

```javascript
function removeQuestionMarks3(string) {
   return string.replace(/\?$/g, '');
}


removeQuestionMarks3('ssup?');		// ssup
removeQuestionMarks3('ssup???');	// ssup??
removeQuestionMarks3('?ssup?');		// ?ssup
removeQuestionMarks3('ssup? ssup?');	// ssup? ssup
```

> `정규표현식 (RegExp)`
>
> `g`: 전역 검색 (Global search)
>
> `$`: 입력의 끝에 일치

<br>

## solution 02

```javascript
const removeQuestionMarks3 = string => string.replace(/\?$/g, '');


removeQuestionMarks3('ssup?');		// ssup
removeQuestionMarks3('ssup???');	// ssup??
removeQuestionMarks3('?ssup?');		// ?ssup
removeQuestionMarks3('ssup? ssup?');	// ssup? ssup
```

<br>

## solution 03

```javascript
function removeQuestionMarks3(string) {
   if (string.charAt(string.length - 1) === '?') {
      return string.slice(0, string.length - 1);
   } else {
      return string;
   }
}


removeQuestionMarks3('ssup?');		// ssup
removeQuestionMarks3('ssup???');	// ssup??
removeQuestionMarks3('?ssup?');		// ?ssup
removeQuestionMarks3('ssup? ssup?');	// ssup? ssup
```

> `.charAt() 메소드`
>
> 지정한 인덱스에서 문자를 반환한다.

<br>

> `.slice() 메소드`
>
> 문자열의 일부를 추출하면서 새로운 문자열을 반환한다.

<br>

## solution 04

```javascript
function removeQuestionMarks3(string) {
   return string.charAt(string.length - 1) === '?' ? string.slice(0, string.length - 1) : string;
}


removeQuestionMarks3('ssup?');		// ssup
removeQuestionMarks3('ssup???');	// ssup??
removeQuestionMarks3('?ssup?');		// ?ssup
removeQuestionMarks3('ssup? ssup?');	// ssup? ssup
```

