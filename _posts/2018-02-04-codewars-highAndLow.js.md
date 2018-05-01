---
layout: post
title: "highAndLow.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

In this little assignment

you are given a string of space separated numbers,

and have to return the highest and lowest number.

<br>

## solution 01

```javascript
function highAndLow(numbers) {
   numbers = numbers.split(' ');
   return `${Math.max(...numbers)} ${Math.min(...numbers)}`;
}


highAndLow('1 2 3 4');	// 4 1
highAndLow('-1 0 1 2');	// 2 -1
```

<br>

## solution 02

```javascript
function highAndLow(numbers) {
   const splitted = numbers.split(' ').map(Number);
   let max = splitted[0];
   let min = splitted[0];
   
   for (let i = 0; i < splitted.length; i++) {
      if (max < splitted[i]) {
         max = splitted[i];
      }
      
      if (min > splitted[i]) {
         min = splitted[i];
      }
   }
   return max + ' ' + min;
}


highAndLow('1 2 3 4');	// 4 1
highAndLow('-1 0 1 2');	// 2 -1
```

> `.map()` 메소드
>
> 배열 내 모든 요소 각각에 대하여
>
> 제공된 함수(callback)를 호출하고,
>
> 그 결과를 모아서 새로운 배열을 반환한다.

<br>

> `.split()` 메소드
>
> 문자열을 부분 문자열로 분할해서 배열로 반환한다.

<br>