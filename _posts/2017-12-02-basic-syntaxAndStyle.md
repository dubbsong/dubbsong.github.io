---
layout: post
title: "syntaxAndStyle.js"
categories: dev
tags: algo
---

#### 객체(object) 알고리즘 문제

<br>

## problem

Fix the syntax & style issues

with the three objects below:

```javascript
var obj1 = {firstName 'Leo', lastName: 'Song'}

var obj2 = {a: 1, b:2 c: 3 d 4}

var obj3 = 

{

animal: 'dog'

noise: 'bark',

age: 3,

type 'Labrador'

}


console.log(obj1);	// SyntaxError: Unexpected string ...
console.log(obj2);	// SyntaxError: Unexpected string ...
console.log(obj3);	// SyntaxError: Unexpected string ...
```

<br>

## solution 01

```javascript
var obj1 = { firstName: 'Leo', lastName: 'Song'};
var obj2 = { a: 1, b: 2, c: 3, d: 4 };
var obj3 = { animal: 'dog', noise: 'bark', age: 3, type: 'Labrador' };


console.log(obj1);	// { firstName: 'Leo', lastName: 'Song'}
console.log(obj2);	// { a: 1, b: 2, c: 3, d: 4 }
console.log(obj3);	// { animal: 'dog', noise: 'bark', age: 3, type: 'Labrador' }
```

<br>

## solution 02

```javascript
var obj1 = {
   firstName: 'Leo',
   lastName: 'Song'
};



var obj2 = {
   a: 1,
   b: 2,
   c: 3,
   d: 4
};



var obj3 = {
   animal: 'dog',
   noise: 'bark',
   age: 3,
   type: 'Labrador'
};
```

