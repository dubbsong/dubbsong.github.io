---
layout: post
title: "addToFrontOfNew.js"
categories: dev
tags: algo
---

#### 배열(array) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function called '`addToFrontOfNew`'.

<br>

Given an array and an element,

'addToFrontOfNew' returns a new array

containing all the elements of the given array,

with the given element added to the front.

<br>

It should be a NEW array instance,

not the original array instance.

<br>

## solution

```javascript
function addToFrontOfNew(array, element) {
   let newArray = array.slice();
   newArray.unshift(element);
   return newArray;
}


addToFrontOfNew([1, 2], 3);	// [3, 1, 2]
```

> `.slice()` 메소드
>
> 문자열의 일부를 추출하면서 새로운 문자열을 반환한다.

<br>

> `.unshift()` 메소드
>
> 하나 이상의 요소(element)를 배열의 시작점에 추가하고 배열의 새 길이(length)를 반환한다.

<br>