---
layout: post
title: "findDelNum.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

An ordered sequence of numbers from 1 to N is given.

<br>

One number might have deleted from it,

then the remaining numbers were mixed.

<br>

Find the number that was deleted.

<br>

If no numbers was deleted from the array and no difference with it,

your function should return the int '`0`'.

<br>

## solution 01

```javascript
function findDelNum(array, mixArray) {
   let result = 0;
   
   for (let i = 0; i < array.length; i++) {
      if (mixArray.indexOf(array[i]) === -1) {
         result = array[i];
      }
   }
   return result;
}


findDelNum([1, 2, 3, 4], [2, 3, 1, 4]);	// 0
findDelNum([1, 2, 3, 4], [2, 3, 1]);	// 4
```

> `.indexOf()` 메소드
>
> 일치하는 인덱스를 반환하고, 존재하지 않으면 -1을 반환한다.

<br>

## solution 02

```javascript
function findDelNum(array, mixArray) {
   for (let i in array) {
      if (mixArray.indexOf(array[i]) === -1) {
         return array[i];
      }
   }
   return 0;
}


findDelNum([1, 2, 3, 4], [2, 3, 1, 4]);	// 0
findDelNum([1, 2, 3, 4], [2, 3, 1]);	// 4
```

<br>

## solution 03

```javascript
function findDelNum(array, mixArray) {
   return array.filter(a => mixArray.indexOf(a) === -1)[0] || 0;
}


findDelNum([1, 2, 3, 4], [2, 3, 1, 4]);	// 0
findDelNum([1, 2, 3, 4], [2, 3, 1]);	// 4
```

> `.filter()` 메소드
>
> 테스트를 통과한 요소로 채워진 새로운 배열을 반환한다.

<br>