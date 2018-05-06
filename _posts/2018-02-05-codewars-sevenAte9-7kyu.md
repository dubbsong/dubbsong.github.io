---
layout: post
title: "sevenAte9.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function that removes every lone 9 that is inbetween 7s.

<br>

## solution 01

```javascript
function sevenAte9(string) {
   let splitted = string.split('');
   
   for (let i = 1; i < splitted.length - 1; i++) {
      if (splitted[i - 1] === '7' && splitted[i] === '9' && splitted[i + 1] === '7') {
         splitted.splice(i, 1);
      }
   }
   return splitted.join('');
}


sevenAte9('79797979');	// 77779
sevenAte9('12347979');	// 1234779
```

> `.splice()` 메소드
>
> 배열에서 요소를 추가/삭제하고, 삭제된 요소를 반환한다.

<br>

## solution 02

```javascript
function sevenAte9(string) {
   return string.replace(/79(?=7)/g, '7');
}


sevenAte9('79797979');	// 77779
sevenAte9('12347979');	// 1234779
```

> 정규표현식 (RegExp)
>
> `replace`: 일치하는 문자열을 replacement로 대체한다.
>
> `?`: 0 또는 1회 반복되는 앞선 문자에 일치한다. (= `{0, 1}`)

<br>