---
layout: post
title: "sumIntegersInString.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Your task is to implement a function

that calculates the sum of the integers

inside a string.

<br>

> Note: only positive integers will be tested.

<br>

## solution 01

```javascript
function sumIntegersInString(string) {
	return (string.match(/\d+/g) || []).reduce((a, b) => a + +b, 0);
}


sumIntegersInString('4ssup 2bro?');	// 6
```

> 정규표현식 (RegExp)
>
> `match`: 정보를 가지고 있는 배열을 반환하거나, 일치하지 않는 부분을 null로 반환한다.
>
> `\d`: 숫자 문자에 일치한다. (= `[0-9]`)
>
> `+`: 1회 이상 연속으로 반복되는 앞선 문자에 일치한다.

<br>

> `.reduce()` 메소드
>
> 왼쪽에서 오른쪽으로 이동하면서
>
> 배열의 각 요소마다 누적 계산값과 함께
>
> 함수를 적용해 하나의 값으로 줄인다.

<br>

## solution 02

```javascript
function sumIntegersInString(string) {
   return string.split(/[^0-9]+/g).reduce((a, b) => a + +b, 0);
}


sumIntegersInString('4ssup 2bro?');	// 6
```

> 정규표현식 (RegExp)
>
> `^`: 입력의 시작에 일치한다.
>
> `[0-9]`: 숫자 문자에 일치한다. (= `\d`)
>
> `[^0-9]`: 숫자 문자가 아닌 문자에 일치한다. (= `\D`)

<br>

## solution 03

```javascript
function sumIntegersInString(string) {
   return string.replace(/\D/g, ' ').split(' ').map(a => Number(a)).reduce((a, b) => a + b);
   console.log(string);
}


sumIntegersInString('4ssup 2bro?');	// 6
```

> 정규표현식 (RegExp)
>
> `\D`: 숫자 문자가 아닌 문자에 일치한다. (= `[^0-9]`)

<br>

## solution 04

```javascript
function sumIntegersInString(string) {
   string = string.match(/\d+/g);
   console.log(string);
   
   if (string === null) return 0;
   
   let result = 0
   
   for (let i = 0; i < string.length; i++) {
      result += Number(string[i]);
   }
   return result;
}


sumIntegersInString('4ssup 2bro?');	// 6
```



