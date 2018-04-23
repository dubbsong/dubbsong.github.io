---
layout: post
title: "joinArrays.js"
categories: dev
tags: algo
---

#### 배열(array) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function called '`joinArrays`'.

<br>

Given two arrays,

'joinArrays' returns an array

with the elements of '`array1`' in order,

followed by the elements in '`array2`'.

<br>

## solution

```javascript
function joinArrays(array1, array2) {
   return array1.concat(array2);
}


joinArrays([1, 2], [3, 4]);	// [1, 2, 3, 4]
```

> `.concat()` 메소드
>
> 주어진 배열이나 값을 기존 배열에 합쳐서 새 배열을 반환한다.

<br>