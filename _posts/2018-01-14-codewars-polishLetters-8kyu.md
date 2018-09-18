---
layout: post
title: "polishLetters.js (8kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 정규표현식(RegExp) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Your task is to change the letters with diacritics:

> ą -> a,
>
> ć -> c,
>
> ę -> e,
>
> ł -> l,
>
> ń -> n,
>
> ó -> o,
>
> ś -> s,
>
> ź -> z,
>
> ż -> z

<br>

And print out the string

without the use of the Polish letters.

<br>

## solution 01

```javascript
const correctLetters = {
   ą: 'a',
   ć: 'b',
   ę: 'e',
   ł: 'l',
   ń: 'n',
   ó: 'o',
   ś: 's',
   ź: 'z',
   ż: 'z'
}


function polishLetters(string) {
   return string.replace(/[ąćęłńóśźż]/g, match => correctLetters[match]);
}


polishLetters('dubbśóńg');	// dubbsong
```

<br>

## solution 02

```javascript
const correctLetters = {
   ą: 'a',
   ć: 'b',
   ę: 'e',
   ł: 'l',
   ń: 'n',
   ó: 'o',
   ś: 's',
   ź: 'z',
   ż: 'z'
}


function polishLetters(string) {
   return string.split('').map((a) => correctLetters[a] || a).join('');
}


polishLetters('dubbśóńg');	// dubbsong
```

