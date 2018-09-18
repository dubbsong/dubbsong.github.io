---
layout: post
title: "filterList.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

In this kata

you will create a function that takes

a list of non-negative integers and strings

and returns a new list

with the strings filtered out.

<br>

## solution 01

```javascript
function filterList(array) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      if (typeof array[i] === 'number') {
         result.push(array[i]);
      }
   }
   return result;
}


filterList([1, 2, 'a', 'b']);	// [1, 2]
```

<br>

## solution 02

```javascript
function filterList(array) {
   return array.filter(a => typeof a === 'number');
}


filterList([1, 2, 'a', 'b']);	// [1, 2]
```

> `.filter()` 메소드
>
> 테스트를 통과한 요소로 채워진 새로운 배열을 반환한다.

<br>