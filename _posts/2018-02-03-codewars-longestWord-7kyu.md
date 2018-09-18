---
layout: post
title: "longestWord.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

When given a string of space separated words,

return the word with the longest length.

<br>

If there are multiple words with the longest length,

return the last instance of the word with the longest length.

<br>

## solution 01

```javascript
function longestWord(string) {
   return string.split(' ').sort((a, b) => a.length - b.length).pop();
}


longestWord('a b c dubbo e');	// dubbo
longestWord('three two one');	// three
longestWord('All good bro?');	// bro?
```

> `.split()` 메소드
>
> 문자열을 부분 문자열로 분할해서 배열로 반환한다.

<br>

> `.sort()` 메소드
>
> 배열의 요소를 적절한 위치에 정렬하고 배열을 반환한다.

<br>

> `.pop()` 메소드
>
> 배열에서 마지막 요소를 제거하고, 제거된 요소를 반환한다.

<br>

## solution 02

```javascript
function longestWord(string) {
   string = string.split(' ');
   let result = '';
   
   for (let i = 0; i < string.length; i++) {
      if (result.length <= string[i].length) {
         result = string[i];
      }
   }
   return result;
}


longestWord('a b c dubbo e');	// dubbo
longestWord('three two one');	// three
longestWord('All good bro?');	// bro?
```

