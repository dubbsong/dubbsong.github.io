---
layout: post
title: "convertDoubleSpaceToSingle.js"
categories: dev
tags: algo
---

#### 문자열(string) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function called '`convertDoubleSpaceToSingle`'.

<br>

Given a string,

'convertDoubleSpaceToSingle' returns 

the passed in string,

with all the double spaces converted to single spaces.

<br>

## solution

```javascript
function convertDoubleSpaceToSingle(string) {
   return string.split('  ').join(' ');
}


convertDoubleSpaceToSingle('Wassup  bro?');	// Wassup bro?
// argument의 'Wassup'과 'bro?' 사이에는 빈 공백이 두 칸이다.
// 출력된 결과의 'Wassup'과 'bro?' 사이에는 빈 공백이 한 칸이다.
```

