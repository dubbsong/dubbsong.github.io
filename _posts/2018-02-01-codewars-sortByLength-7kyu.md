---
layout: post
title: "sortByLength.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function

that takes an array of strings

as an argument and returns a sorted array

containing the same strings,

ordered from shortest to longest.

<br>

## solution

```javascript
function sortByLength(array) {
   return array.sort((a, b) => a.length - b.length);
}


sortByLength(['brother', 'ssup']);	// ['ssup', 'brother']
sortByLength(['How', 'are', 'you?']);	// ['How', 'are', 'you?']
```

> `.sort()` 메소드
>
> 배열의 요소를 적절한 위치에 정렬하고 배열을 반환한다.

<br>