---
layout: post
title: "countAllCharacters.js"
categories: dev
tags: algo
---

#### 객체(object) 활용 알고리즘 문제

<br>

## problem

Write a function called '`countAllCharacters`'.

<br>

Given a string,

'countAllCharacters' returns an object

where each key is a character in the given string.

<br>

The value of each key should be how many times

each character appeared in the given string.

<br>

> Notes:
>
> If given an empty string,
>
> 'countAllCharacters' return an empty object.

<br>

## solution

```javascript
function countAllCharacters(string) {
   let result = {};
   
   for (let i = 0; i < string.length; i++) {
      let key = string[i];
      result[key] = (result[key] || 0) + 1;
   }
   return result;
}


countAllCharacters('ssup');	// { s: 2, u: 1, p: 1 }
```

