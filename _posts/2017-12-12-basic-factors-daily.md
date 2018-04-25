---
layout: post
title: "factors.js"
categories: dev
tags: algo
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

In this problem,

you have to find the factors of '`integer`' down to the '`limit`'

including the limiting number.

<br>

There will be no negative numbers.

<br>

Return the result as an array of numbers

in ascending order.

<br>

If the limit is more than the integer,

return an empty list.

<br>

## solution

```javascript
function factors(integer, limit) {
   let result = [];
   
   for (let i = limit; i <= integer; i++) {
      if (integer % i === 0) {
         result.push(i);
      }
   }
   return result;
}


factors(10, 2);	// [2, 5, 10]
factors(10, 3);	// [5, 10]
factors(10, 4);	// [5, 10]
```

> `.push()` 메소드
>
> 배열의 끝에 엘리먼트를 추가하고 배열의 변경된 길이를 반환한다.

<br>