---
layout: post
title: "joinArrayOfArrays.js"
categories: dev
tags: algo
---

#### 배열(array) + 반복문 (for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function called '`joinArrayOfArrays`'.

<br>

Given an array of arrays,

'joinArrayOfArrays' returns a single array

containing the elements of the nested array.

<br>

## solution

```javascript
function joinArrayOfArrays(array) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      result = result.concat(array[i]);
   }
   return result;
}


joinArrayOfArrays([[1, 2], [true, false], ['a', 'b']]);	// [1, 2, true, false, 'a', 'b']
```

> `.concat()` 메소드
>
> 주어진 배열이나 값을 기존 배열에 합쳐서 새 배열을 반환한다.

<br>