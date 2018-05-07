---
layout: post
title: "flatten.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) + 연산자(operator) 활용 알고리즘 문제

<br>

## problem

Write a function

that flattens an '`Array`' of '`Array`' objects

into a flat '`Array`'.

<br>

Your function must only do one level of flattening.

<br>

## solution 01

```javascript
function flatten(array) {
   return [].concat(...array);
}


flatten([1, 2]);			// [1, 2]
flatten([[1], ['a'], [2]]);	// [1, 'a', 2]
flatten([[[1], [2]], 3]);	// [[1], [2], 3]
```

> .concat() 메소드
>
> 주어진 배열을 기존 배열에 합쳐서 새로운 배열을 반환한다.

<br>

## solution 02

```javascript
function flatten(array) {
   let result = [];
   
   for (let i in array) {
      result = result.concat(array[i]);
   }
   return result;
}


flatten([1, 2]);			// [1, 2]
flatten([[1], ['a'], [2]]);	// [1, 'a', 2]
flatten([[[1], [2]], 3]);	// [[1], [2], 3]
```

<br>

## solution 03

```javascript
function flatten(array) {
   let result = [];
   
   for (let i = 0; i < array.length; i++) {
      if (array[i] instanceof Array) {
         for (let j = 0; j < array[i].length; j++) {
            result.push(array[i][j]);
         }
      } else {
         result.push(array[i]);
      }
   }
   return result;
}


flatten([1, 2]);			// [1, 2]
flatten([[1], ['a'], [2]]);	// [1, 'a', 2]
flatten([[[1], [2]], 3]);	// [[1], [2], 3]
```

> `instanceof` 연산자
>
> 개체가 특정 클래스의 인스턴스인지 테스트하고, 불린 값을 반환한다.

<br>

## solution 04

```javascript
function flatten(array) {
   return [].concat.apply([], array);
}


flatten([1, 2]);			// [1, 2]
flatten([[1], ['a'], [2]]);	// [1, 'a', 2]
flatten([[[1], [2]], 3]);	// [[1], [2], 3]
```

> `.apply()` 메소드
>
> 함수를 호출해서 지정된 개체를 함수의 this 값으로 대체하고,
>
> 지정된 배열을 함수의 인수로 대체한다.

<br>