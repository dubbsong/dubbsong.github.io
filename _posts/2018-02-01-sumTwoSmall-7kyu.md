---
layout: post
title: "sumTwoSmall.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Create a function that returns

the sum of the two lowest positive numbers

given an array of minimum 4 integers.

<br>

No floats or empty arrays will be passed.

<br>

## solution

```javascript
function sumTwoSmall(numbers) {
   numbers = numbers.sort((a, b) => a - b);
   return numbers[0] + numbers[1];
}


sumTwoSmall([1, 2, 3, 4]);	// 3
sumTwoSmall([4, 8, 2, 0]);	// 2
```

> `.sort()` 메소드
>
> 배열의 요소를 정렬하고 배열을 반환한다.

<br>