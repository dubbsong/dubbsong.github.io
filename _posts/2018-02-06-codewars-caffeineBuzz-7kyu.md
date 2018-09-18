---
layout: post
title: "caffeineBuzz.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) 활용 알고리즘 문제

<br>

## problem

Complete the function '`caffeineBuzz`',

which takes a non-zero integer as it's one argument.

<br>

If the integer is divisible by 3, return the string '`Java`'.

<br>

If the integer is divisible by 3 and divisible by 4, return the string '`Coffee`'.

<br>

If the integer is one of the above and is even,

add '`Script`' to the end of the string.

<br>

Otherwise, return the string '`mocha_missing!`'.

<br>

## solution 01

```javascript
function caffeineBuzz(n) {
   if (n % 12 === 0) return 'CoffeeScript';
   if (n % 6 === 0) return 'JavaScript';
   if (n % 3 === 0) return 'Java';
   return 'mocha_missing';
}


caffeineBuzz(1);	// mocha_missing!
caffeineBuzz(3);	// Java
caffeineBuzz(6);	// JavaScript
caffeineBuzz(12);	// CoffeeScript
```

<br>

## solution 02

```javascript
function caffeineBuzz(n) {
   let string = 'mocha_missing!';
   
   if (n % 3 === 0) {
      if (n % 4 === 0) {
         string = 'Coffee';
      } else {
         string = 'Java';
      }
      
      if (n % 2 === 0) {
         string = string + 'Script';
      }
   }
   return string;
}


caffeineBuzz(1);	// mocha_missing!
caffeineBuzz(3);	// Java
caffeineBuzz(6);	// JavaScript
caffeineBuzz(12);	// CoffeeScript
```

<br>

## solution 03

```javascript
function caffeineBuzz(n) {
   if (n % 3 === 0) {
      if (n % 4 === 0) {
         return (n % 2 === 0) ? 'CoffeeScript' : 'Coffee';
      } else {
         return (n % 2 === 0) ? 'JavaScript' : 'Java';
      }
   } else {
      return 'mocha_missing!';
   }
}


caffeineBuzz(1);	// mocha_missing!
caffeineBuzz(3);	// Java
caffeineBuzz(6);	// JavaScript
caffeineBuzz(12);	// CoffeeScript
```



