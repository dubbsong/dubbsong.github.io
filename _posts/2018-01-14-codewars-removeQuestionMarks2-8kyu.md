---
layout: post
title: "removeQuestionMarks2.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 정규표현식(RegExp) 활용 알고리즘 문제

<br>

## problem

Remove '`n`' question marks

in the sentece

from left to right.

<br>

'`n`' is positive integer.

<br>

## solution 01

```javascript
function removeQuestionMarks2(string, n) {
   return n > 0 ? removeQuestionMarks2(string.replace('?', ''), n - 1) : string;
}


removeQuestionMarks2('ssup?', 1);			// ssup
removeQuestionMarks2('ssup???', 1);			// ssup??
removeQuestionMarks2('?ssup?', 1);			// ssup?
removeQuestionMarks2('??ssup?? ??ssup??', 100);	// ssup ssup
```

<br>

## solution 02

```javascript
const removeQuestionMarks2 = (string, n) => n > 0 ? removeQuestionMarks2(string.replace('?', ''), n - 1) : string;


removeQuestionMarks2('ssup?', 1);			// ssup
removeQuestionMarks2('ssup???', 1);			// ssup??
removeQuestionMarks2('?ssup?', 1);			// ssup?
removeQuestionMarks2('??ssup?? ??ssup??', 100);	// ssup ssup
```

<br>

## solution 03

```javascript
const removeQuestionMarks2 = (string, n) => n > 0 ? removeQuestionMarks2(string.replace(/\?/, ''), n - 1) : string;


removeQuestionMarks2('ssup?', 1);			// ssup
removeQuestionMarks2('ssup???', 1);			// ssup??
removeQuestionMarks2('?ssup?', 1);			// ssup?
removeQuestionMarks2('??ssup?? ??ssup??', 100);	// ssup ssup
```

