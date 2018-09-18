---
layout: post
title: "sentenceSmash.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 문자열(string) 알고리즘 문제

<br>

## problem

Write a method smash

that takes an array of words

and smashes them together into a sentence

and returns the sentences.

<br>

You can ignore any need to sanitize words

or add punctuation,

but you should add spaces between each word.

<br>

Be careful, there shouldn't be a space

at the beginning or the end of the sentence.

<br>

## solution 01

```javascript
function sentenceSmash(string) {
   return string.join(' ');
}


sentenceSmash(['Wassup', 'bro?']);	// Wassup bro?
sentenceSmash(['How', 'are', 'you?']);	// How are you?
```

<br>

## solution 02

```javascript
const sentenceSmash = string => string.join(' ');


sentenceSmash(['Wassup', 'bro?']);	// Wassup bro?
sentenceSmash(['How', 'are', 'you?']);	// How are you?
```

