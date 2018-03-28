---
layout: post
title: "keep.js"
categories: dev
tags: algo
---

#### 반복문(for loop) + 조건문(if) + 배열(array) 알고리즘 문제

<br>

## problem

Write a function '`keep`'

that "keeps" certain elements in an array.

The function will need to take two arguments,

an array, and something else.

<br>

The second argument will be a function

that is used to determine which elements to keep.

<br>

If the condition function returns true

when called on an element of the array,

that element should be present in the array

that you return from the function.

<br>

## solution 01

```javascript
function isEven(element) {
   if (element % 2 === 0) {
      return true;
   }
}


function keep(array, condition) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      if (condition(array[i]) === true) {
         result.push(array[i]);
      }
   }
   return result;
}


keep([1, 2, 3, 4], isEven);	// [2, 4]
```

<br>

## solution 02

```javascript
// 아직 이해불가. 유택스한테 물어볼 예정.

function isEven(element) {
   if (element % 2 === 0) {
      return true;
   }
}


function keep(array, condition) {
   return array.filter((a) => { if (condition(a)) return a });
}


keep([1, 2, 3, 4], isEven);	// [2, 4]
```



