---
layout: post
title: "tripleTrouble.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 문자열(string) 알고리즘 문제

<br>

## problem

Create a function that will return a string

that combines all of the letters

of the three inputed strings in groups.

<br>

Taking the first letter of all of the inputs

and grouping them next to each other.

<br>

Do this for every letter, see example below.

> Input: 'aa', 'bb', 'cc'
>
> Output: 'abcabc'

<br>

## solution 01

```javascript
function tripleTrouble(one, two, three) {
   let result = '';
   one = one.split('');
   two = two.split('');
   three = three.split('');
   
   for (let i = 0; i < one.length; i++) {
      result += one[i] + two[i] + three[i];
   }
   return result;
}


tripletrouble('aa', 'bb', 'cc');	// abcabc
tripletrouble('bm', 'aa', 'tn');	// batman
```

<br>

## solution 02

```javascript
function tripleTrouble(one, two, three) {
   let result = '';
   
   for (let i = 0; i < one.length; i++) {
      result += one.charAt(i) + two.charAt(i) + three.charAt(i);
   }
   return result;
}


tripletrouble('aa', 'bb', 'cc');	// abcabc
tripletrouble('bm', 'aa', 'tn');	// batman
```

