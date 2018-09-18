---
layout: post
title: "sumWithoutHighAndLow.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 불린(boolean) + 반복문(for loop) 알고리즘 문제

<br>

## problem

Sum all numbers of the array

except the highest and the lowest element.

<br>

If array is empty, null or None,

or if only 1 Element exists, return 0.

<br>

> `.sort()` method
>
> const fruits = ['Banana', 'Lemon', 'Apple'];
>
> console.log(fruits.sort());	// ['Apple', 'Banana', 'Lemon']

<br>

> const numbers = [8, 1, 2, 10];
>
> console.log(numbers.sort());	// [1, 10, 2, 8] `* Unicode에서 10이 2보다 앞에 위치`

<br>

> const numbers = [4, 2, 5, 1, 3];
>
> numbers.sort((a, b) => a - b);
>
> console.log(numbers);	// [1, 2, 3, 4, 5]

<br>

## solution 01

```javascript
function sumWithoutHighAndLow(array) {
   if (array === null) {
      return 0;
   } else if (array.length < 2) {
      return 0;
   } else {
      array = array.sort((a, b) => a - b);
      let result = 0;
      
      for (let i = 0; i < array.length - 1; i++) {
         result += array[i];
      }
      return result;
   }
}


sumWithoutHighAndLow([ ]);		 // 0
sumWithoutHighAndLow([4]);		 // 0
sumWithoutHighAndLow([1, 4, 2, 3]);	// 5 (2 + 3)
```

<br>

## solution 02

```javascript
const sumWithoutHighAndLow = array => array ? array.sort((a, b) => a - b).slice(1, -1).reduce((a, b) => a + b, 0) : 0;


sumWithoutHighAndLow([ ]);		 // 0
sumWithoutHighAndLow([4]);		 // 0
sumWithoutHighAndLow([1, 4, 2, 3]);	// 5 (2 + 3)
```



