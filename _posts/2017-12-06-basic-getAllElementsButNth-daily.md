---
layout: post
title: "getAllElementsButNth.js"
categories: dev
tags: algo
---

#### 배열(array) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function called '`getAllElementsButNth`'.

<br>

Given an array and an index,

'getAllElementsButNth' returns an array

with all the elements but the '`n`'th.

<br>

## solution

```javascript
function getAllElementsButNth(array, n) {
   array.splice(n, 1);
   return array;
}


getAllElementsButNth([1, 2, 3], 1);	// [1, 3]
```

> `.splice()` 메소드
>
> 배열에 있는 요소(element)를 삭제하거나 배열에 새 요소를 추가한다.

<br>