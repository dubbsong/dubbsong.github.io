---
layout: post
title: "sortGiftCode.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function called '`sortGiftCode`' that accepts a string

containing up to 26 unique alphabetical characters,

and returns a string containing the same characters

in alphabetical order.

<br>

## solution 01

```javascript
function sortGiftCode(code) {
   return code.split('').sort().join('');
}


sortGiftCode('dbac');	// abcd
sortGiftCode('ssup');	// pssu
```

> `.split()` 메소드
>
> 문자열을 부분 문자열로 분할해서 배열로 반환한다.

<br>

> `.sort()` 메소드
>
> 배열의 요소를 적절한 위치에 정렬하고, 배열을 반환한다.

<br>

> `.join()` 메소드
>
> 배열의 모든 요소를 연결해 하나의 문자열로 만들고, 문자열을 반환한다.

<br>

## solution 02

```javascript
function sortGiftCode(code) {
   return code.split('').sort().toString().replace(/,/g, '');
}


sortGiftCode('dbac');	// abcd
sortGiftCode('ssup');	// pssu
```

> `.toString()` 메소드
>
> 숫자를 문자열로 반환한다.

<br>

> `.replace()` 메소드 **or** 정규표현식 `replace`
>
> 일치하는 문자열을 replacement로 대체한다.

<br>

## solution 03

```javascript
function sortGiftCode(code) {
   let result = [];
   
   for (let i = 0; i < code.length; i++) {
      result.push(code.substr(i, 1));
   }
   return result.sort().join('');
}


sortGiftCode('dbac');	// abcd
sortGiftCode('ssup');	// pssu
```

> `.substr()` 메소드
>
> 지정된 위치의 문자부터, 지정된 수만큼의 문자들을 반환한다.

<br>