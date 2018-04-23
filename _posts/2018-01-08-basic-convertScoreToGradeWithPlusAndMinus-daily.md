---
layout: post
title: "convertScoreToGradeWithPlusAndMinus.js"
categories: dev
tags: algo
---

#### 숫자(number) + 문자열(string) 활용 알고리즘 문제

<br>

## problem

Write a function called '`convertScoreToGradeWithPlusAndMinus`'.

<br>

Given a score,

'convertScoreToGradeWithPlusAndMinus' returns

a string representing the letter grade

corresponding to the given score.

<br>

> Notes:
>
> (100 - 90) === 'A'
>
> (89 - 80) === 'B'
>
> (79 - 70) === 'C'
>
> (69 - 60) === 'D'
>
> (59 - 0) === 'F'

<br>

If the given score is

greater than 100 or less than 0,

it should return '`INVALID SCORE`'.

<br>

If the score is

between the 0 and 2 (inclusive) of a given range,

return the letter with a '`-`'.

<br>

If the score is

between the 8 and 9 (inclusive) of a given range,

return the letter with a '`+`'.

<br>

There is no '`F+`' and there is no '`F-`'.

<br>

## solution

```javascript
function convertScoreToGradeWithPlusAndMinus(score) {
   let result = '';
   
   if (score > 100 || score < 0) {
      return 'INVALID SCORE';
   }
   
   if (score >= 90) {
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
   
   if (score === 100 || score % 10 >= 8) {
      result += '+';
   } else if (score % 10 <= 2) {
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

