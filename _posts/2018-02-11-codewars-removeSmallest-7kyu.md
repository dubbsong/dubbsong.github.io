---
layout: post
title: "removeSmallest.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Given an array of integers,

remove the smallest value.

<br>

Do not mutate the original array.

<br>

If there are multiple elements

with the same value,

remove the one with a lower index.

<br>

If you get an empty array,

return an empty array.

<br>

Don't change the order of the elements that are left.

<br>

## solution

```javascript
function removeSmallest(numbers) {
   const min = Math.min(...numbers);
   numbers.splice(numbers.indexOf(min), 1);
   return numbers;
}


removeSmallest([1, 2, 3, 4]);	// [2, 3, 4]
removeSmallest([4, 3, 2, 4]);	// [4, 3, 4]
removeSmallest([2, 1, 2, 1]);	// [2, 2, 1]
```

> `.splice()` 메소드
>
> 배열에서 요소를 추가/삭제하고, 삭제된 요소를 반환한다.

<br>

> `.indexOf()` 메소드
>
> 일치하는 인덱스를 반환하고, 존재하지 않으면 -1을 반환한다.

<br>