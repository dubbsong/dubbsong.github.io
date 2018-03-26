---
layout: post
title: "scoreToGrade.js"
categories: dev
tags: algo
---

#### 조건문 + boolean 알고리즘 문제

<br>

## problem

Write a function called '`scoreToGrade`'

that accepts a number as a parameter

and returns a string representing

a letter grade corresponding to that score.

<br>

> 'A' >= 90
>
> 'B' >= 80
>
> 'C' >= 70
>
> 'D' >= 60
>
> 'F' < 60

<br>

## solution

```javascript
function scoreToGrade(score) {
   if (score >= 90) {
      return 'A';
   } else if (score >= 80) {
      return 'B';
   } else if (score >= 70) {
      return 'C';
   } else if (score >= 60) {
      return 'D';
   } else {
      return 'F';
   }
}


scoreToGrade(95);	// A
scoreToGrade(72);	// C
scoreToGrade(55);	// F
```

