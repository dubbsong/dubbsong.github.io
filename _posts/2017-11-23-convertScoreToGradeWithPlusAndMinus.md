---
layout: post
title: "convertScoreToGradeWithPlusAndMinus.js"
categories: dev
tags: algo
---

#### 조건문 + boolean 알고리즘 문제

<br>

## problem

Write a function called '`convertScoreToGradeWithPlusAndMinus`'.

Given a score,

'convertScoreToGradeWithPlusAndMinus' returns

a string representing the letter grade corresponding

to the given score.

<br>

> (100 ~ 90) -> 'A'
>
> (89 ~ 80) -> 'B'
>
> (79 ~ 70) -> 'C'
>
> (69 ~ 60) -> 'D'
>
> (59 ~ 0) -> 'F'

<br>

\* <u>If the given score is greater than 100 or less than 0,</u>

<u>it should return 'INVALID SCORE'.</u>

<br>

\* <u>If the score is between the 0 and 2 (inclusive) of a given range,</u>

<u>return the letter with a '-'.</u>

<br>

\* <u>If the score is between the 8 and 9 (inclusive) of a given range,</u>

<u>return the letter with a '+'.</u>

<br>

\* <u>There is no F+ and there is no F-.</u>

<br>

## solution 01

```javascript
function convertScoreToGradeWithPlusAndMinus(score) {
   if (score >= 0 && score <= 59) {
      return 'F';
   } else if (score >= 60 && score <= 62) {
      return 'D-';
   } else if (score >= 63 && score <= 67) {
      return 'D';
   } else if (score >= 68 && score <= 69) {
      return 'D+';
   } else if (score >= 70 && score <= 72) {
      return 'C-';
   } else if (score >= 73 && score <= 77) {
      return 'C';
   } else if (score >= 78 && score <= 79) {
      return 'C+';
   } else if (score >= 80 && score <= 82) {
      return 'B-';
   } else if (score >= 83 && score <= 87) {
      return 'B';
   } else if (score >= 88 && score <= 89) {
      return 'B+';
   } else if (score >= 90 && score <= 92) {
      return 'A-';
   } else if (score >= 93 && score <= 97) {
      return 'A';
   } else if (score >= 98 && score <= 100) {
      return 'A+';
   } else {
      return 'INVALID SCORE';
   }
}


convertScoreToGradeWithPlusAndMinus(101);	// INVALID SCORE
convertScoreToGradeWithPlusAndMinus(-19);	// INVALID SCORE
convertScoreToGradeWithPlusAndMinus(98);	// A+
convertScoreToGradeWithPlusAndMinus(97);	// A
convertScoreToGradeWithPlusAndMinus(93);	// A
convertScoreToGradeWithPlusAndMinus(92);	// A-
convertScoreToGradeWithPlusAndMinus(60);	// D-
convertScoreToGradeWithPlusAndMinus(59);	// F
```

<br>

## solution 02

```javascript
function convertScoreToGradeWithPlusAndMinus(score) {
   let result = '';
   
   if (score > 100 || score < 0) {
      return 'INVALID SCORE';
   } else if (score === 100) {
      return 'A+';
   } else if (score >= 90) {
      result += 'A';
   } else if (score >= 80) {
      result += 'B';
   } else if (score >= 70) {
      result += 'C';
   } else if (score >= 60) {
      result += 'D';
   } else {
      return 'F';
   }
   
   if (score.toString()[1] >= 8) {
      result += '+';
   } else if (score.toString()[1] <= 2) {
      result += '-';
   }
   return result;
}


convertScoreToGradeWithPlusAndMinus(101);	// INVALID SCORE
convertScoreToGradeWithPlusAndMinus(-19);	// INVALID SCORE
convertScoreToGradeWithPlusAndMinus(98);	// A+
convertScoreToGradeWithPlusAndMinus(97);	// A
convertScoreToGradeWithPlusAndMinus(93);	// A
convertScoreToGradeWithPlusAndMinus(92);	// A-
convertScoreToGradeWithPlusAndMinus(60);	// D-
convertScoreToGradeWithPlusAndMinus(59);	// F
```

