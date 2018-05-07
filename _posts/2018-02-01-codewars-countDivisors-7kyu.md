---
layout: post
title: "countDivisors.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) 알고리즘 문제

<br>

## problem

Find the number of divisors of a positive integer '`n`'.

<br>

> divisor (약수)
>
> 나머지 없이 나눌 수 있는 정수.

<br>

## solution 01

```javascript
function countDivisors(n) {
   let count = 0;
   
   for (let i = 1; i <= n; i++) {
      if (n % i === 0) {
         count += 1;
      }
   }
   return count;
}


countDivisors(1);	// 1
countDivisors(4);	// 3 (1, 2, 4)
countDivisors(5);	// 2 (1, 5)
countDivisors(10);	// 4 (1, 2, 5, 10)
```

<br>

## solution 02

```javascript
function countDivisors(n) {
   let count = 1;
   
   for (let i = 0; i <= n / 2; i++) {
      if (n % i === 0) {
         count += 1;
      }
   }
   return count;
}


countDivisors(1);	// 1
countDivisors(4);	// 3 (1, 2, 4)
countDivisors(5);	// 2 (1, 5)
countDivisors(10);	// 4 (1, 2, 5, 10)
```

