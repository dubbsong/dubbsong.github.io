---
layout: post
title: "reverseLetter.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Given a string, reverse it omitting

all non-alphabetic characters.

<br>

## solution 01

```javascript
function reverseLetter(string) {
   return string.match(/[a-z]/g).reverse().join('');
}


reverseLetter('br123o');	// orb
reverseLetter('4ssup8');	// puss
```

> 정규표현식 (RegExp)
>
> `match`: 정보를 가지고 있는 배열을 반환하거나, 일치하지 않는 부분을 null로 반환한다.

<br>

> `.reverse()` 메소드
>
> 배열의 요소 순서를 반전시킨다.

<br>

> `.join()` 메소드
>
> 배열의 모든 요소를 연결해 하나의 문자열로 만들고, 문자열을 반환한다.

<br>

## solution 02

```javascript
function reverseLetter(string) {
   return string.replace(/[^a-z]/g, '').split('').reverse().join('');
}


reverseLetter('br123o');	// orb
reverseLetter('4ssup8');	// puss
```

> 정규표현식 (RegExp)
>
> `replace`: 일치하는 문자열을 replacement로 대체한다.

<br>

> `.split()` 메소드
>
> 문자열을 부분 문자열로 분할해서, 배열로 반환한다.

<br>

## solution 03

```javascript
function reverseLetter(string) {
   return [...string].reduce((a, b) => /[a-z]/g.test(b) ? b + a : a, '');
}


reverseLetter('br123o');	// orb
reverseLetter('4ssup8');	// puss
```

> `.reduce()` 메소드
>
> 왼쪽에서 오른쪽으로 이동하면서
>
> 배열의 각 요소마다 누적 계산값과 함께
>
> 함수를 적용해 하나의 값으로 줄인다.

<br>

> 정규표현식 (RegExp)
>
> `test`: 일치하는 문자열을 검사하고 true나 false를 반환한다.

<br>