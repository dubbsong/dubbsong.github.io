---
layout: post
title: "countWords.js"
categories: dev
tags: algo
---

#### 반복문(for loop) + 조건문(if) + 객체(object) 알고리즘 문제

<br>

## problem

Write a function '`countWords`' that

when given a string as an argument,

returns an object where keys are the words

in the string and values are the number

of occurrences of that word within the string.

<br>

You will want to make use of the string method, '`split`'.

Try 'Hello hello'.split(' ')

in the console to see how it works.

<br>

Implement a case-Insensitive version of 'countWords'

by using the following string method: `toLowercase();`

<br>

## solution 01 (countWords)

```javascript
function countWords(string) {
   let obj = {};
   let splitted = string.split(' ');
   
   for (let i = 0; i < splitted.length; i++) {
      if (obj.hasOwnProperty(splitted[i])) {
         obj[splitted[i]]++;
      } else {
         obj[splitted[i]] = 1;
      }
   }
   return obj;
}


countWords('hello hello');	// { hello: 2 }
countWords('Hello hello');	// { Hello: 1, hello: 1 }
countWords('Wassup bro');	// { Wassup: 1, bro: 1 }
```

<br>

## solution 01 (countWordsCaseInsensitive)

```javascript
function countWordsCaseInsensitive(string) {
   let obj = {};
   let splitted = string.toLowerCase().split(' ');
   
   for (let i = 0; i < splitted.length; i++) {
      if (obj.hasOwnProperty(splitted[i])) {
         obj[splitted[i]]++;
      } else {
         obj[splitted[i]] = 1;
      }
   }
   return obj;
}


countWordsCaseInsensitive('hello hello');	// { hello: 2 }
countWordsCaseInsensitive('Hello hello');	// { hello: 2 }
countWordsCaseInsensitive('Wassup bro');	// { wassup: 1, bro: 1 }
```

<br>

## solution 02 (countWords)

```javascript
function countWords(string) {
   let obj = {};
   let splitted = string.split(' ');
   
   for (let i of splitted) {
      if (obj.hasOwnProperty(i)) {
         obj[i]++;
      } else {
         obj[i] = 1;
      }
   }
   return obj;
}


countWords('hello hello');	// { hello: 2 }
countWords('Hello hello');	// { Hello: 1, hello: 1 }
countWords('Wassup bro');	// { Wassup: 1, bro: 1 }
```

<br>

## solution 02 (countWordsCaseInsensitive)

```javascript
function countWordsCaseInsensitive(string) {
   let obj = {};
   let splitted = string.toLowerCase().split(' ');
   
   for (let i of splitted) {
      if (obj.hasOwnProperty(i)) {
         obj[i]++;
      } else {
         obj[i] = 1;
      }
   }
   return obj;
}


countWordsCaseInsensitive('hello hello');	// { hello: 2 }
countWordsCaseInsensitive('Hello hello');	// { hello: 2 }
countWordsCaseInsensitive('Wassup bro');	// { wassup: 1, bro: 1 }
```

<br>

## solution 03 (countWords)

```javascript
function countWords(string) {
   let obj = {};
   let splitted = string.split(' ');
   
   for (let i of splitted) {
      obj.hasOwnProperty(i) ? obj[i]++ : obj[i] = 1;
   }
   return obj;
}


countWords('hello hello');	// { hello: 2 }
countWords('Hello hello');	// { Hello: 1, hello: 1 }
countWords('Wassup bro');	// { Wassup: 1, bro: 1 }
```

<br>

## solution 03 (countWordsCaseInsensitive)

```javascript
function countWordsCaseInsensitive(string) {
   let obj = {};
   let splitted = string.toLowerCase().split(' ');
   
   for (let i of splitted) {
      obj.hasOwnProperty(i) ? obj[i]++ : obj[i] = 1;
   }
   return obj;
}


countWordsCaseInsensitive('hello hello');	// { hello: 2 }
countWordsCaseInsensitive('Hello hello');	// { hello: 2 }
countWordsCaseInsensitive('Wassup bro');	// { wassup: 1, bro: 1 }
```

