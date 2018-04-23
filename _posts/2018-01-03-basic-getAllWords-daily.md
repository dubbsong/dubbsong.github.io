---
layout: post
title: "getAllWords.js"
categories: dev
tags: algo
---

#### 문자열(string) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function called '`getAllWords`'.

<br>

Given a sentence,

'getAllWords' returns an array

containing every word in the sentence.

<br>

> Note:
>
> If given an empty string, it should return an empty array.

<br>

## solution

```javascript
function getAllWords(string) {
   return string ? string.split(' ') : [];
}


getAllWords('Wassup bro?');	// ['Wassup', 'bro?]
```

> `.split()` 메소드
>
> 문자열을 부분 문자열로 분할하고, 배열로 반환한다.

<br>