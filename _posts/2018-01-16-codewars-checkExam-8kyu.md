---
layout: post
title: "checkExam.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for loop) +불린(boolean) + 메소드 활용 알고리즘 문제

<br>

## problem

The first input array contains the correct answers to an exam.

The second one is '`answer`' array and contains student's answers.

The two array are not empty and are the same length.

<br>

Return the score for this array of answers,

giving '`+4`' for each correct answer,

'`-1`' for each incorrect answer,

and '`+0`' for each blank answer.

<br>

If the score < 0, return 0.

<br>

## solution 01

```javascript
function checkExam(array1, array2) {
   let result = 0;
   
   for (let i = 0; i < array1.length; i++) {
      if (array1[i] === array2[i]) {
         result += 4;
      } else if (array2[i] === '') {
         result += 0;
      } else {
         result -= 1; 
      }
   }
   return result < 0 ? 0 : result;
}


checkExam(['a', 'a'], ['b', 'b']);	// 0
checkExam(['a', 'a'], ['a', 'b']);	// 3
checkExam(['a', 'a'], ['a', 'a']);	// 8
```

<br>

## solution 02

```javascript
function checkExam(array1, array2) {
   let result = array2.reduce((score, answer, i) => {
      if (array1[i] === answer) {
         return score += 4;
      } else if (answer === '') {
         return score += 0;
      } else {
         return score -= 1;
      }
   }, 0);
   return result < 0 ? 0 : result;
}


checkExam(['a', 'a'], ['b', 'b']);	// 0
checkExam(['a', 'a'], ['a', 'b']);	// 3
checkExam(['a', 'a'], ['a', 'a']);	// 8
```

