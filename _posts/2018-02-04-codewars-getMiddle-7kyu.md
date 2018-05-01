---
layout: post
title: "getMiddle.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

You are going to be given a word.

<br>

Your job is

to return the middle character of the word.

<br>

If the word's length is odd,

return the middle character.

<br>

If the word's length is even,

return the middle 2 characters.

<br>

> Examples
>
> getMiddle('test');		// es
>
> getMiddle('testing');	// t

<br>

## solution 01

```javascript
function getMiddle(string) {
   const middle = string.length / 2;
   return string.length % 2 === 0
   	? string.slice(middle - 1, middle + 1)
   	: string.charAt(Math.floor(middle));
}


getMiddle('ssup');	// su
getMiddle('ssup?');	// u
```

> `.slice()` 메소드
>
> 문자열의 일부를 추출하면서 새로운 문자열을 반환한다.

<br>

> `.charAt()` 메소드
>
> 지정한 인덱스에서 문자를 반환한다.

<br>

> `.Math.floor()` 메소드
>
> 가장 가까운 정수로 버림한 다음 결과를 반환한다.

<br>

## solution 02

```javascript
function getMiddle(string) {
   const middle = Math.floor(string.length / 2);
   return string.length % 2 === 0
   	? string.slice(middle - 1, middle + 1)
   	: string.slice(middle, middle + 1);
}


getMiddle('ssup');	// su
getMiddle('ssup?');	// u
```

<br>

## solution 03

```javascript
function getMiddle(string) {
   return string.slice((string.length - 1) / 2, string.length / 2 + 1);
}


getMiddle('ssup');	// su
getMiddle('ssup?');	// u
```

