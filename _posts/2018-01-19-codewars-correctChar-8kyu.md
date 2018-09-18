---
layout: post
title: "correctChar.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 반복문(for) + 정규표현식(RegExp) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Your task is correct the errors

in the digitised text.

<br>

You only have to handle the following mistakes:

> '`S`' is misinterpreted as '`5`'
>
> '`O`' is misinterpreted as '`0`'
>
> '`I`' is misinterpreted as '`1`'

<br>

## solution 01

```javascript
function correctChar(string) {
   return string.replace(/5/g, 'S').replace(/0/g, 'O').replace(/1/g, 'I');
}


correctChar('PAR15');	// PARIS
correctChar('L0ND0N');	// LONDON
```

<br>

## solution 02

```javascript
function correctChar(string) {
   const corrections = { '5': 'S', '0': 'O', '1': 'I' };
   return string.replace(/5|0|1/g, char => corrections[char]);
}


correctChar('PAR15');	// PARIS
correctChar('L0ND0N');	// LONDON
```

<br>

## solution 03

```javascript
function correctChar(string) {
   return [...string].map(a => ({ '5': 'S', '0': 'O', '1': 'I' })[a] || a).join('');
}


correctChar('PAR15');	// PARIS
correctChar('L0ND0N');	// LONDON
```

<br>

## solution 04

```javascript
function correctChar(string) {
   for (let i = 0; i < string.length; i++) {
      string = string.replace('5', 'S');
      string = string.replace('0', 'O');
      string = string.replace('1', 'I');
   }
   return string
}


correctChar('PAR15');	// PARIS
correctChar('L0ND0N');	// LONDON
```

<br>

## solution 05

```javascript
function correctChar(string) {
   let result = '';
   
   for (let i = 0; i < string.length; i++) {
      if (string.charAt(i) === '5') {
         result += 'S';
      } else if (string.charAt(i) === '0') {
         result += 'O';
      } else if (string.charAt(i) === '1') {
         result += 'I';
      } else {
         result += string.charAt(i);
      }
   }
   return result;
}


correctChar('PAR15');	// PARIS
correctChar('L0ND0N');	// LONDON
```

<br>

## solution 06

```javascript
function correctChar(string) {
   let result = [];
   splitted = string.split('');
   
   for (let i = 0; i < splitted.length; i++) {
      if (splitted[i].includes('5')) {
         result.push(splitted[i].replace('5', 'S'));
      } else if (splitted[i].includes('0')) {
         result.push(splitted[i].replace('0', 'O'));
      } else if (splitted[i].includes('1')) {
         result.push(splitted[i].replace('1', 'I'));
      } else {
         result.push(splitted[i]);
      }
   }
   return result.join('');
}


correctChar('PAR15');	// PARIS
correctChar('L0ND0N');	// LONDON
```

