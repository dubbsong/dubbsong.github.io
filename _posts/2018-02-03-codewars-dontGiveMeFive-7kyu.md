---
layout: post
title: "dontGiveMeFive.js"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

In this kata you get the start number

and the end number of a region

and should return the count of all numbers

except numbers with a `5` in it.

<br>

The start and the end number are both inclusive.

<br>

## solution 01

```javascript
function dontGiveMeFive(start, end) {
   let result = 0;
   
   for (let i = start; i <= end; i++) {
      if (!/5/.test(i)) {
         result += 1;
      }
   }
   return result;
}


dontGiveMeFive(4, 8);	// 4
dontGiveMeFive(4, 9);	// 5
```

> `정규표현식 (RegExp)`
>
> `test`: 일치하는 문자열을 검사하는 메소드. (true나 false를 반환)

<br>

## solution 02

```javascript
function dontGiveMeFive(start, end) {
   let result = [];
   
   for (let i = start; i <= end; i++) {
      if (!i.toString().includes('5')) {
         result.push(i);
      }
   }
   return result.length;
}


dontGiveMeFive(4, 8);	// 4
dontGiveMeFive(4, 9);	// 5
```

> `.toString()` 메소드
>
> 숫자를 문자열로 반환한다.

<br>

> `.includes()` 메소드
>
> 배열에 특정 요소가 포함되어 있는지 여부를 확인해서 true 또는 false를 반환한다.

<br>