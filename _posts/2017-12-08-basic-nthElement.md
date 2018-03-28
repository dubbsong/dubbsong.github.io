---
layout: post
title: "nthElement.js"
categories: dev
tags: algo
---

#### 배열(array) 알고리즘 문제

<br>

## problem

Write a function called '`nth`'

that accepts an array and an index as parameters,

and returns the element at that index.

<br>

## solution

```javascript
const animals = ['cat', 'dog', 'elephant'];

function nth(array, index) {
   return array[index];
}


nth(animals, 0);		// cat
nth(animals, 2);		// elephant
nth(animals, 2) === 'elephant';	// true
```

