---
layout: post
title: "getAllLetters.js"
categories: dev
tags: algo
---

#### 문자열(string) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function called '`getAllLetters`'.

<br>

Given a word,

'getAllLetters' returns an array

containing every character in the word.

<br>

> Notes:
>
> If given an empty string, it should return an empty array.

<br>

## solution

```javascript
function getAllLetters(string) {
   return string.split('');
}


getAllLetters('ssup');	// ['s', 's', 'u', 'p']
```

> `.split()` 메소드
>
> 문자열을 부분 문자열로 분할하고, 배열로 반환한다.

<br>