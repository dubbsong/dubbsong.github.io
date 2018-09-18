---
layout: post
title: "sentencify.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) + 정규표현식(RegExp) 활용 알고리즘 문제

<br>

## problem

Your function should:

1. Capitalise the first letter of the first word.
2. Add a period(.) to the end of the sentence.
3. Join the words into a complete string, with spaces.
4. Do no other manipulation on the words.

<br>

## solution

```js
function sentencify(words) {
   return words.join(' ').replace(/^[a-z]/, a => a.toUpperCase()) + '.';
}


sentencify(['i', 'am', 'Batman']);	// I am Batman.
```

> `정규표현식 (RegExp)`
>
> `replace`: 일치하는 문자열을 replacement로 대체한다.
>
> `^`: 입력의 시작에 일치한다.

<br>