---
layout: post
title: "letterGradeHelper.js"
categories: dev
tags: algo
---

#### 조건문(if) + 불린(boolean) 알고리즘 문제

<br>

## problem

When we do lots of repetitive things,

that's a clear signal that there's a better way.

Write a helper function 'letterGradeHelper'

that accepts two arguments, letter and score.

<br>

## solution

```javascript
function letterGradeHelper(letter, score) {
   const str = score.toString();
   
   if (str[str.length - 1] >= 8) {
      return letter + '+';
   } else if (str[str.length - 1] <= 2) {
      return letter + '-';
   } else {
      return letter;
   }
}


letterGradeHelper('A', 98);	// A+
letterGradeHelper('A', 97);	// A
letterGradeHelper('A', 92);	// A-
letterGradeHelper('D', 60);	// D-
letterGradeHelper('ssup', 100);	// ssup-
```

