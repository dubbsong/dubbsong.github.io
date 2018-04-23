---
layout: post
title: "isReallyNaN.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 기본자료형 number 알고리즘 문제

<br>

## problem

Write a function '`isReallyNaN`'

that returns '`true`' only if passed in

an argument that evalutes to '`NaN`',

and returns '`false`' otherwise.

<br>

## solution 01

```javascript
function isReallyNaN(value) {
   return value !== value;
}


isReallyNaN(1234);		// false
isReallyNaN('1234');		// false
isReallyNaN(undefined);	// false
isReallyNaN(NaN);		// true
```

<br>

## solution 02

```javascript
function isReallyNaN(value) {
   if (!isNaN(value)) return false;
   if (value === Number) return false;
   if (value === undefined) return false;
   if (value === Function) return false;
   if (value === Object) return false;
   if (typeof(value) === 'string') return false;
   if (typeof(value) === 'function') return false;
   if (typeof(value) === 'object') return false;
   if (isNaN(value)) return true;
   else return false;
}


isReallyNaN(1234);		// false
isReallyNaN('1234');		// false
isReallyNaN(undefined);	// false
isReallyNaN(NaN);		// true
```

> `NaN`
>
> Not a Number (숫자가 아님).
>
> 연산 과정에서 잘못된 입력을 받았음을 나타낸다.
>
> 숫자로 변환될 수 없다면 NaN을 반환한다.

<br>