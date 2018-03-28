---
layout: post
title: "stringReverse.js"
categories: dev
tags: algo
---

#### 배열(array) + 문자열(string) 알고리즘 문제

<br>

## problem

Read about the '`join`' method on MDN

and use it to implement a function

that accepts a string as an argument

and returns that string reversed.

<br>

> `.split('')`
>
> var string = 'Hello world! How are you?';
>
> string.split(' ', 3);	// ['Hello', 'world!', 'How']

<br>

> `.reverse()`
>
> var array = ['one', 'two', 'three'];
>
> array.reverse();	// ['three', 'two', 'one']

<br>

> `.join('')`
>
> var array = ['Sam', 'Leo', 'Ralph'];
>
> array.join(', ');	// 'Sam, Leo, Ralph'

<br>

## solution

```javascript
function stringReverse(string) {
   return string.split('').reverse().join('');
}


stringReverse('Wassup bro?');	// ?orb pussaW
```

