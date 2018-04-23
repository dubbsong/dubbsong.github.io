---
layout: post
title: "fixPipe.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Each pipe should be connecting,

since the levels ascend,

you can assume every number

in the sequence after the first index

will be greater than the previous

and that there will be no duplicates.

<br>

Given the a list of '`numbers`',

return the list so that the values increment

by 1 for each index up to the maximum value.

<br>

## solution 01

```javascript
function fixPipe(numbers) {
   const first = numbers[0];
   const last = numbers[numbers.length - 1];
   let result = [];
   
   for (let i = first; i <= last; i++) {
      result.push(i);
   }
   return result;
}


fixPipe([1, 4]);	// [1, 2, 3, 4]
fixPipe([1, 2, 4]);	// [1, 2, 3, 4]
fixPipe([1, 3, 4]);	// [1, 2, 3, 4]
```

<br>

## solution 02

```javascript
function fixPipe(numbers) {
   const first = numbers.shift();
   const last = numbers.pop();
   let result = [];
   
   for (let i = first; i <= last; i++) {
      result.push(i);
   }
   return result;
}


fixPipe([1, 4]);	// [1, 2, 3, 4]
fixPipe([1, 2, 4]);	// [1, 2, 3, 4]
fixPipe([1, 3, 4]);	// [1, 2, 3, 4]
```

> `.shift()` 메소드
>
> 배열에서 첫 번째 요소를 제거하고, 제거된 요소를 반환한다.

<br>

> `.pop()` 메소드
>
> 배열에서 마지막 요소를 제거하고, 제거된 요소를 반환한다.

<br>