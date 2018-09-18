---
layout: post
title: "removeEveryOther.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Take an array and remove every second element out of that array.

Always keep the first element and start removing with the next element.

<br>

> `.splice()` method
>
> const array = [1, 2, 3, 4, 5, 6];
>
> array.splice(2, 2, 8, 8);
>
> console.log(array);	// [1, 2, 8, 8, 5, 6]

<br>

> `.filter()` method
>
> function isBigEnough(value) { return value >= 10; }
>
> let filtered = [8, 9, 10, 11, 12].filter(isBigEnough);
>
> console.log(filtered);	// [10, 11, 12]

<br>

## solution 01

```javascript
function removeEveryOther(array) {
   let result = [];
   
   for (let i = 0; i < array.length; i += 2) {
      result.push(array[i]);
   }
   return result;
}


removeEveryOther([]);			 // []
removeEveryOther([1, 2]);		 // [1]
removeEveryOther([1, 2, 3, 4, 5, 6]);	// [1, 3, 5]
removeEveryOther(['a', 'b', 'c', 'd']);	// ['a', 'c']
```

<br>

## solution 02

```javascript
function removeEveryOther(array) {
   for (let i = 0; i < array.length; i++) {
      array.splice(i, 1);
   }
   return array;
}


removeEveryOther([]);			 // []
removeEveryOther([1, 2]);		 // [1]
removeEveryOther([1, 2, 3, 4, 5, 6]);	// [1, 3, 5]
removeEveryOther(['a', 'b', 'c', 'd']);	// ['a', 'c']
```

<br>

## solution 03

```javascript
function removeEveryOther(array) {
   return array.filter((a, b) => b % 2 === 0);
}


removeEveryOther([]);			 // []
removeEveryOther([1, 2]);		 // [1]
removeEveryOther([1, 2, 3, 4, 5, 6]);	// [1, 3, 5]
removeEveryOther(['a', 'b', 'c', 'd']);	// ['a', 'c']
```



