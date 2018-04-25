---
layout: post
title: "iqTest.js"
categories: dev
tags: algo
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Bob is preparing to pass IQ test.

<br>

The most frequent task in this test is to find out

which one of the given numbers differs from the others.

<br>

Bob observed that one number usually differs

from the others in evenness.

<br>

Help Bob to check his answers,

he needs a program that among the given numbers finds one

that is different in evenness,

and return a position of this number.

<br>

Keep in mind

that your task is to help Bob solve a real IQ test,

which means indexes of the elements start from 1.

<br>

```javascript
// Examples:

iqTest('2 4 7 8');	// 3 (Third number is odd)
iqTest('1 2 1 1');	// 2 (Second number is even)
```

<br>

## solution

```javascript
function iqTest(numbers) {
   const splitted = numbers.split(' ');
   
   const even = splitted.filter(function(element) {
      return element % 2 === 0;
   })
   
   const odd = splitted.filter(function(element) {
      return element % 2 === 1;
   })
   return even.length === 1
   	? splitted.indexOf(even[0]) + 1
   	: splitted.indexOf(odd[0]) + 1;
}


iqTest('1 2 1 1');	// 2 (Second number is even)
iqTest('2 3 4 8');	// 2 (Second number is odd)
```

> `.split()` 메소드
>
> 문자열을 부분 문자열로 분할하고 배열로 반환한다.

<br>

> `.filter()` 메소드
>
> 제공된 함수로 구현된 테스트를 통과하는 배열의 요소를 반환한다.

<br>

> `.indexOf()` 메소드
>
> 배열이나 문자열에서 지정된 요소의 인덱스 값을 반환한다.
>
> 존재하지 않으면 -1을 반환한다.

<br>

