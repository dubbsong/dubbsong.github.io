---
layout: post
title: "twoToOne.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Take 2 strings '`string1`' and '`string2`'

including only letters from '`a`' to '`z`'.

<br>

Return a new '`sorted`' string,

the longest possible,

containing distinct letters.

<br>

## solution 01

```javascript
function twoToOne(string1, string2) {
   let sumString = string1 + string2;
   let string = sumString.split('');
   let result = [];
   
   string.map((a, b) => {
      if (!result.includes(a)) {
         result.push(a);
      }
   })
   return result.sort().join('');
}


twoToOne('dcba', 'bcad');	// abcd
twoToOne('ssup', 'wassup');	// apsuw
```

<br>

## solution 02

```javascript
function twoToOne(string1, string2) {
   return Array.from(new Set(string1 + string2)).sort().join('');
}


twoToOne('dcba', 'bcad');	// abcd
twoToOne('ssup', 'wassup');	// apsuw
```

> `Array.from()` 메소드
>
> 유사 배열 혹은 반복가능한 객체로부터 새 배열을 반환한다.

<br>

> `new Set()` 메소드
>
> 어떤 형이든 유일한 값을 저장할 수 있다.

<br>

## solution 03

```javascript
function twoToOne(string1, string2) {
   return [...new Set(string1 + string2)].sort().join('');
}


twoToOne('dcba', 'bcad');	// abcd
twoToOne('ssup', 'wassup');	// apsuw
```



