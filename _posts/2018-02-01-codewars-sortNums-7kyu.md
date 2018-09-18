---
layout: post
title: "sortNums.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Finish the solution

so that it sorts the passed in array of numbers.

<br>

If the function passes in an empty array or null value

then it should return an empty array.

<br>

## solution 01

```javascript
function sortNums(array) {
   return array ? array.sort((a, b) => a - b) : [];
}


sortNums([1, 2, 10, 50, 5]);	// [1, 2, 5, 10, 50]
sortNums(null);	// []
```

> `.sort()` 메소드
>
> 배열의 요소를 적절한 위치에 정렬하고, 배열을 반환한다.

<br>

## solution 02

```javascript
function sortNums(array) {
   let result = [];
   
   if (array === null) {
      return result;
   } else {
      return array.sort((a, b) => a - b);
   }
}


sortNums([1, 2, 10, 50, 5]);	// [1, 2, 5, 10, 50]
sortNums(null);	// []
```

