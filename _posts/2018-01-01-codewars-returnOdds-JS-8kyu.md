---
layout: post
title: "returnOdds.js (8kyu)"
categories: codewars
tags: Algorithm
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Return the odds from a list.

<br>

## solution 01

```javascript
function returnOdds(array) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      if (array[i] % 2 !== 0) {
         result.push(array[i]);
      }
   }
   return result;
}


console.log(returnOdds([]));		// []
console.log(returnOdds([1, 2, 3, 4]));	// [1, 3]
```

> `.push()` 메소드
>
> 배열의 끝에 새 요소를 추가하고, 새 길이를 반환한다.

<br>

## solution 02

```javascript
function returnOdds(array) {
   return array.filter(a => a % 2 !== 0);
}


console.log(returnOdds([]));		// []
console.log(returnOdds([1, 2, 3, 4]));	// [1, 3]
```

> `.filter()` 메소드
>
> 테스트를 통과한 요소로 채워진 새로운 배열을 반환한다.

<br>

## solution 03

```javascript
function returnOdds(array) {
   return array.filter(a => a % 2);
}


console.log(returnOdds([]));		// []
console.log(returnOdds([1, 2, 3, 4]));	// [1, 3]
```

<br>

## solution 04

```javascript
const returnOdds = array => array.filter(a => a % 2);


console.log(returnOdds([]));		// []
console.log(returnOdds([1, 2, 3, 4]));	// [1, 3]
```

<br>