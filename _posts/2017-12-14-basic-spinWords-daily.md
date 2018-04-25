---
layout: post
title: "spinWords.js"
categories: dev
tags: algo
---

#### 조건문(if) + 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a function

that takes in a string of one or more words,

and returns the same string,

but with all five or more letter words reversed.

<br>

Strings passed in will consist of only letters and spaces.

<br>

Spaces will be included only when more than one word is present.

<br>

## solution

```javascript
function spinWords(string) {
   let splitted = string.split(' ');
   let result = '';
   
   for (let i = 0; i < splitted.length; i++) {
      let word = splitted[i];
      result += word.length >= 5
      	? word.split('').reverse().join('')
      	: word;
      
      if (i !== splitted.length - 1) {
         result += ' ';
      }
   }
   return result;
}


spinWords('This is a test');		// This is a test
spinWords('This is another test');	// This is rehtona test
```

