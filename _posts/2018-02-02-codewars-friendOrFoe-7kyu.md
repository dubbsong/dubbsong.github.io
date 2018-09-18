---
layout: post
title: "friendOrFoe.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Make a program that filters a list of strings

and returns a list with only your friends name in it.

<br>

If a name has exactly 4 letters in it,

you can be sure that it has to be a friend of yours!

<br>

> Note:
>
> keep the original order of names in the output.

<br>

## solution 01

```javascript
function friendOrFoe(friends) {
   return friends.filter(a => a.length === 4);
}


friendOrFoe(['Sam', 'Leo', 'Song']);	// ['Song']
```

> `.filter()` 메소드
>
> 테스트를 통과한 요소로 채워진 새로운 배열을 반환한다.

<br>

## solution 02

```javascript
function friendOrFoe(friends) {
   let result = [];
   
   for (let i = 0; i < friends.length; i++) {
      if (friends[i].length === 4) {
         result.push(friends[i]);
      }
   }
   return result;
}


friendOrFoe(['Sam', 'Leo', 'Song']);	// ['Song']
```

