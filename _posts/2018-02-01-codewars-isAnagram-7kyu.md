---
layout: post
title: "isAnagram.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

An anagram is the result of rearranging the letters

of a word to produce a new word.

<br>

> Note: anagrams are case insensitive.

<br>

Complete the function to return '`true`'

if the two arguments given are anagrams of the each other;

return '`false`' otherwise.

<br>

## solution 01

```javascript
function isAnagram(test, original) {
   const t = test.toLowerCase().split('').sort().join('');
   const o = original.toLowerCase().split('').sort().join('');
   
   return t === o ? true : false;
}


isAnagram('aWsups', 'Wassup');	// true
isAnagram('bWsups', 'Wassup');	// false
```

> `.toLowerCase()` 메소드
>
> 모든 영문자를 소문자로 변환한다.

<br>

> `.split()` 메소드
>
> 문자열을 부분 문자열로 분할해서, 배열로 변환한다.

<br>

> `.sort()` 메소드
>
> 배열의 요소를 적절한 위치에 정렬하고, 배열을 반환한다.

<br>

> `.join()` 메소드
>
> 배열의 모든 요소를 연결해 하나의 문자열로 만들고, 문자열을 반환한다.

<br>

## solution 02

```javascript
function isAnagram(test, original) {
   return test.sortString() === original.sortString();
}

String.prototype.sortString = function() {
   return this.toLowerCase().split('').sort().join('');
}


isAnagram('aWsups', 'Wassup');	// true
isAnagram('bWsups', 'Wassup');	// false
```

