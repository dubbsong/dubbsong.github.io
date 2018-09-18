---
layout: post
title: "sumOccurOnce.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

You will be given an array of numbers

in which two numbers occur once

and the rest occur only twice.

<br>

Your task will be to return the sum of the numbers

that occur only once.

<br>

## solution 01

```javascript
function sumOccurOnce(array) {
   let result = 0;
   
   for (let i = 0; i < array.length; i++) {
      if (array.indexOf(array[i]) === array.lastIndexOf(array[i])) {
         result += array[i];
      }
   }
   return result;
}


sumOccurOnce([4, 2, 1, 1, 2]);	// 4
sumOccurOnce([2, 1, 1, 3]);	// 5
```

> `.indexOf()` 메소드
>
> 일치하는 인덱스를 반환하고, 일치하는 값이 없으면 -1을 반환한다.

<br>

> `.lastIndexOf()` 메소드
>
> 반대 방향으로 찾기 시작해서 일치하는 마지막 인덱스를 반환한다.
>
> 일치하는 값이 없으면 -1을 반환한다.

<br>

## solution 02

```javascript
function sumOccurOnce(array) {
   array = array.sort();
   console.log(array);
   let result = 0;
   
   for (let i = 0; i < array.length; i++) {
      if (array[i] === array[i + 1]) {
         i++;
      } else {
         result += array[i];
      }
   }
   return result;
}


sumOccurOnce([4, 2, 1, 1, 2]);
// [1, 1, 2, 2, 4]
// 4
sumOccurOnce([2, 1, 1, 3]);
// [1, 1, 2, 3]
// 5
```

> `.sort()` 메소드
>
> 배열의 요소를 적절한 위치에 정렬하고, 배열을 반환한다.

<br>

## solution 03

```javascript
function sumOccurOnce(array) {
   array = array.sort();
   console.log(array);
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      if (array[i] != array[i + 1]) {
         result.push(array[i]);
      } else {
         i++;
      }
   }
   return result.reduce((a, b) => a + b);
}


sumOccurOnce([4, 2, 1, 1, 2]);
// [1, 1, 2, 2, 4]
// 4
sumOccurOnce([2, 1, 1, 3]);
// [1, 1, 2, 3]
// 5
```

> `.reduce()` 메소드
>
> 왼쪽에서 오른쪽으로 이동하면서
>
> 배열의 각 요소마다 누적 계산값과 함께
>
> 함수를 적용해 하나의 값으로 줄인다.

<br>

## solution 04

```javascript
function sumOccurOnce(array) {
   return array.filter(a => array.indexOf(a) === array.lastIndexOf(a)).reduce((a, b) => a + b, 0);
}


sumOccurOnce([4, 2, 1, 1, 2]);	// 4
sumOccurOnce([2, 1, 1, 3]);	// 5
```

> `.filter()` 메소드
>
> 테스트를 통과한 요소로 채워진 새로운 배열을 반환한다.

<br>