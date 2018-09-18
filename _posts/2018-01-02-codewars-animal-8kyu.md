---
layout: post
title: "animal.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 객체(object) + ES6 문법 + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Give you a function '`animal`',

accept 1 parameter '`obj`',

and return a string like this:

`This pink pig has 4 legs.`

<br>

## solution 01

```javascript
var obj = { name: 'pig', color: 'pink', legs: 4 }


function animal(obj) {
   return `This ${obj.color} ${obj.name} has ${obj.legs} legs.`;
}


animal(obj);	// This pink pig has 4 legs.
```

<br>

## solution 02

```javascript
var obj = { name: 'pig', color: 'pink', legs: 4 }


const animal = obj => `This ${obj.color} ${obj.name} has ${obj.legs} legs.`;


animal(obj);	// This pink pig has 4 legs.
```

<br>

## solution 03

```javascript
var obj = { name: 'pig', color: 'pink', legs: 4 }


function animal(obj) {
   let {name, color, legs} = obj;
   return `This ${color} ${name} has ${legs} legs.`;
}


animal(obj);	// This pink pig has 4 legs.
```

<br>

## solution 04

```javascript
var obj = { name: 'pig', color: 'pink', legs: 4 }


function animal({name, color, legs}) {
   return `This ${color} ${name} has ${legs} legs.`;
}


animal(obj);	// This pink pig has 4 legs.
```

<br>

## solution 05

```javascript
var obj = { name: 'pig', color: 'pink', legs: 4 }


function animal(obj) {
   return ['This', obj.color, obj.name, 'has', obj.legs, 'legs.'].join(' ');
}


animal(obj);	// This pink pig has 4 legs.
```

