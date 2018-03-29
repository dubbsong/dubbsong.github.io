---
layout: post
title: "fullName.js"
categories: dev
tags: algo
---

#### 객체(object) 알고리즘 문제

<br>

## problem

Write a function '`fullName`'

that takes a person object as an argument,

and returns that person's full name as a string.

<br>

What happens if you pass a person object

to fullName that doesn't have a middle name?

<br>

Your 'fullName' function should work correctly

regardless of whether or not the person has a middle name.

<br>

## solution

```javascript
var Sam = {
   name: {
      first: 'Samuel',
      middle: 'D.',
      last: 'Azor'
   },
   age: 28
}



function fullName(person) {
   return person.name.middle
   ? person.name.first + ' ' + person.name.middle + ' ' + person.name.last
   : person.name.first + ' ' + person. name.last;
}





fullName(Sam);	// Samuel D. Azor
```

