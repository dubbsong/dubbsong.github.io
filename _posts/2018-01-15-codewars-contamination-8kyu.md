---
layout: post
title: "contamination.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 정규표현식(RegExp) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

An AI has infected a text with a character.

This text is now fully mutated to this character.

<br>

If the text or the character are empty,

return an empty string.

<br>

There will never be a case

when both are empty as nothing is going on.

<br>

\* <u>The character is a string of length 1 or an empty string.</u>

<br>

## solution 01

```javascript
function contamination(text, char) {
   return char.repeat(text.length);
}


contamination('', '?');		// ''
contamination('?', '');		// ''
contamination('ssup', '?');	// ????
```

<br>

## solution 02

```javascript
function contamination(text, char) {
   return text.split('').map(a => a = char).join('');
}


contamination('', '?');		// ''
contamination('?', '');		// ''
contamination('ssup', '?');	// ????
```

<br>

## solution 03

```javascript
function contamination(text, char) {
   return text.replace(/./g, char);
}


contamination('', '?');		// ''
contamination('?', '');		// ''
contamination('ssup', '?');	// ????
```

> `정규표현식 (Regular Expression)`
>
> `.`: 다음 줄 문자를 제외한 어떤 하나의 문자에 일치

<br>

## solution 04

```javascript
const contamination = (text, char) => text.replace(/./g, char);


contamination('', '?');		// ''
contamination('?', '');		// ''
contamination('ssup', '?');	// ????
```

<br>

## solution 05

```javascript
function contamination(text, char) {
   return text !== '' && char !== '' ? char.repeat(text.length) : '';
}


contamination('', '?');		// ''
contamination('?', '');		// ''
contamination('ssup', '?');	// ????
```

