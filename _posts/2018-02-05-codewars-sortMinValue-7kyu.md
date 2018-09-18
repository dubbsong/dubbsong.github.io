---
layout: post
title: "sortMinValue.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Given a list of digits, return the smallest number

that could be formed these digits,

using the digits only once (ignore duplicates).

<br>

## solution 01

```javascript
function sortMinValue(array) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      if (result.indexOf(array[i]) === -1) {
         result.push(array[i]);
      }
   }
   return Number(result.sort().join(''));
}


sortMinValue([4, 6, 5, 6]);	// 456
sortMinValue([4, 8, 1, 4]);	// 148
```

> `.sort()` 메소드
>
> 배열의 요소를 적절한 위치에 정렬하고, 배열을 반환한다.

<br>

> `.indexOf()` 메소드
>
> 일치하는 인덱스를 반환하고, 일치하는 값이 없으면 -1을 반환한다.

<br>

> `.push()` 메소드
>
> 배열의 끝에 새 요소를 추가하고, 새 길이를 반환한다.

<br>

> `.join()` 메소드
>
> 배열의 모든 요소를 연결해 하나의 문자열로 만들고, 문자열을 반환한다.

<br>

## solution 02

```javascript
function sortMinValue(array) {
   array = array.sort();
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      if (result.indexOf(array[i]) === -1) {
         result.push(array[i]);
      }
   }
   return Number(result.join(''));
}


sortMinValue([4, 6, 5, 6]);	// 456
sortMinValue([4, 8, 1, 4]);	// 148
```

