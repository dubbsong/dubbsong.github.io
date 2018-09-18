---
layout: post
title: "averages.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a method,

that gets an array of integer-numbers

and return an array of the averages

of each integer-number and his follower,

if there is one.

<br>

## solution 01

```javascript
function averages(numbers) {
   let result = [];
   
   if (numbers === null) return result;
   if (numbers.length <= 1) return result;
   
   for (let i = 0; i < numbers.length - 1; i++) {
      result.push((numbers[i] + numbers[i + 1]) / 2);
   }
   return result;
}


averages([]);		// []
averages([1]);		// []
averages([1, 3, 5, 1]);	// [2, 4, 3]
```

<br>

## solution 02

```javascript
function averages(numbers) {
   let result = [];
   
   if (numbers === null) return result;
   if (numbers.length <= 1) return result;
   
   for (let i = 1; i < numbers.length; i++) {
      result.push((numbers[i - 1] + numbers[i]) / 2);
   }
   return result;
}


averages([]);		// []
averages([1]);		// []
averages([1, 3, 5, 1]);	// [2, 4, 3]
```

