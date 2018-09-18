---
layout: post
title: "sortByValueAndIndex.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Your task is to sort an array of integer numbers

by the product of the value and the index of the positions.

<br>

For sorting the index starts at 1, NOT at 0.

The sorting has to be ascending.

<br>

> Example
>
> Input: 9, 5, 1, 4
>
> 9 => 9 * 1 = 9   -> Output Position 2
>
> 5 => 5 * 2 = 10 -> Output Position 3
>
> 1 => 1 * 3 = 3   -> Output Position 1
>
> 4 => 4 * 4 = 16 -> Output Position 4

<br>

## solution 01

```javascript
function sortByValueAndIndex(array) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      result.push([array[i], array[i] * (i + 1)]);
      console.log(result);
   }
   return result.sort((a, b) => a[1] - b[1]).map(a => a[0]);
}


// [[9, 9]]
// [[9, 9], [5, 10]]
// [[9, 9], [5, 10], [1, 3]]
// [[9, 9], [5, 10], [1, 3], [4, 16]]
sortByValueAndIndex([9, 5, 1, 4]);	// [1, 9, 5, 4]
```

> `.push()` 메소드
>
> 배열의 끝에 새 요소를 추가하고, 새 길이를 반환한다.

<br>

> `.sort()` 메소드
>
> 배열의 요소를 적절한 위치에 정렬하고, 배열을 반환한다.

<br>

> `.map()` 메소드
>
> 배열 내 모든 요소 각각에 대하여
>
> 제공된 함수(callback)를 호출하고,
>
> 그 결과를 모아서 새로운 배열을 반환한다.

<br>

## solution 02

```javascript
function sortByValueAndIndex(array) {
   return array
   	.map((a, b) => [a, a * (b + 1)])
   	.sort((a, b) => a[1] - b[1])
   	.map(a => a[0]);
}


sortByValueAndIndex([9, 5, 1, 4]);	// [1, 9, 5, 4]
```



