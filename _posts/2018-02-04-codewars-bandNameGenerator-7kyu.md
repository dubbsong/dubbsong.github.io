---
layout: post
title: "bandNameGenerator.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 메소드(method) 활용 알고리즘 문제

<br>

## problem

My friend wants a new band name for her band.

She like bands that use the formula:

`"The" + a noun with the first letter capitalized.`

<br>

> for example:
>
> "dolphin" -> "The Dolphin"

<br>

However, when a noun STARTS and ENDS with the same letter,

she likes to repeat the noun twice

and connect them together with the first and last letter,

combined into one word.

<br>

> for example:
>
> "alaska" -> "Alaskalaska"

<br>

Complete the function

that takes a noun as a string,

and returns her preferred band name written

as a string.

<br>

## solution 01

```javascript
function bandNameGenerator(name) {
   return name[0] === name[name.length - 1]
   	? name[0].toUpperCase() + name.slice(1).repeat(2)
   	: 'The ' + name[0].toUpperCase() + name.slice(1);
}


bandNameGenerator('ssup');	// The Ssup
bandNameGenerator('tart');	// Tartart
bandNameGenerator('qq');	// Qqq
```

> `.toUpperCase()` 메소드
>
> 문자열에 있는 모든 영문자를 대문자로 변환한다.

<br>

> `.slice()` 메소드
>
> 문자열의 일부를 추출하면서 새로운 문자열을 반환한다.

<br>

> `.repeat()` 메소드
>
> 지정된 횟수만큼 복사본을 가진 새 문자열을 반환한다.

<br>

## solution 02

```javascript
function bandNameGenerator(name) {
   return name[0] === name.slice(-1)
   	? `${name[0].toUpperCase()}${name.slice(1, -1)}${name}`
   	: `The ${name[0].toUpperCase()}${name.slice(1)}`;
}


bandNameGenerator('ssup');	// The Ssup
bandNameGenerator('tart');	// Tartart
bandNameGenerator('qq');	// Qqq
```

