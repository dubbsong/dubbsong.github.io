---
layout: post
title: "UpperLowerNumSpecialChar.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

You will be given a string

and your task will be to return a list of ints detailing the count of

`uppercase letters`, `lowercase`, `numbers` and `special characters`, as follows.

<br>

## solution

```javascript
function UpperLowerNumSpecialChar(string) {
   let u = string.match(/[A-Z]/g) || [];
   let l = string.match(/[a-z]/g) || [];
   let n = string.match(/[0-9]/g) || [];
   let s = string.match(/[^A-Za-z0-9]/g) || [];
   
   return [u.length, l.length, n.length, s.length];
}


UpperLowerNumSpecialChar('W@ssup8688');	// [1, 4, 4, 1]
```

> 정규표현식 (RegExp)
>
> `match`: 정보를 가지고 있는 배열을 반환하거나, 일치하지 않는 부분을 null로 반환한다.

<br>