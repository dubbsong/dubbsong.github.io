---
layout: post
title: "select.js"
categories: dev
tags: algo
---

#### 객체(object) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function called '`select`'.

<br>

Given an array and an object,

'select' returns a new object whose properties are those

in the given object AND whose keys are present

in the given array.

<br>

> Notes:
>
> If keys are present in the given array,
>
> but are not in the given object,
>
> it should ignore them.
>
> It does not modify the passed in object.

<br>

## solution

```javascript
let array = ['a', 'd'];
let object = { a: 1, b: 2, c: 3, d: 4 };

function select(array, object) {
   let result = {};
   
   for (let i = 0; i < array.length; i++) {
      let key = array[i];
      
      if (object.hasOwnProperty(key)) {
         result[key] = object[key];
      }
   }
   return result;
}


select(array, object);	// { a: 1, d: 4 }
```

> `.hasOwnProperty()` 메소드
>
> 객체가 특정 프로퍼티를 가지고 있는지를 나타내는 불리언 값을 반환한다.

<br>