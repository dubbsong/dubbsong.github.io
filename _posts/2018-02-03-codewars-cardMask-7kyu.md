---
layout: post
title: "cardMask.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 반복문(for loop) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Your task is to write a function '`cardMask`',

which changes all but the last four characters into '`#`'.

<br>

## solution 01

```javascript
function cardMask(cardNumber) {
   cardNumber = cardNumber.split('');
   
   for (let i = 0; i < cardNumber.length - 4; i++) {
      cardNumber[i] = '#';
   }
   cardNumber = cardNumber.join('');
   return cardNumber;
}


cardMask('35902105131');	// #######5131
cardMask('1');			// 1
cardMask('');			// ''
cardMask('Wassup');	// ##ssup
```

<br>

## solution 02

```javascript
function cardMask(cardNumber) {
   return '#'.repeat(cardNumber.slice(0, -4).length) + cardNumber.slice(-4);
}


cardMask('35902105131');	// #######5131
cardMask('1');			// 1
cardMask('');			// ''
cardMask('Wassup');	// ##ssup
```

> `.repeat()` 메소드
>
> 지정된 횟수만큼 복사본을 가진 새 문자열을 반환한다.

<br>

## solution 03

```javascript
function cardMask(cardNumber) {
   return cardNumber.slice(0, -4).replace(/./g, '#') + cardNumber.slice(-4);
}


cardMask('35902105131');	// #######5131
cardMask('1');			// 1
cardMask('');			// ''
cardMask('Wassup');	// ##ssup
```

> `.slice()` 메소드
>
> 문자열의 일부를 추출하면서 새로운 문자열을 반환한다.

<br>

> 정규표현식 (RegExp)
>
> `replace`: 일치하는 문자열을 replacement로 대체한다.
>
> `.`: 개행 문자를 제외한 어떤 하나의 문자에 일치한다.
>
> `g`: 전역 검색 (Global search)

<br>

## solution 04

```javascript
function cardMask(cardNumber) {
   return cardNumber.replace(/.(?=....)/g, '#');
}


cardMask('35902105131');	// #######5131
cardMask('1');			// 1
cardMask('');			// ''
cardMask('Wassup');	// ##ssup
```

> 이해 필요

<br>

## solution 05

```javascript
function cardMask(cardNumber) {
   return cardNumber.replace(/.(?={4})/g, '#');
}


cardMask('35902105131');	// #######5131
cardMask('1');			// 1
cardMask('');			// ''
cardMask('Wassup');	// ##ssup
```

> 이해 필요

<br>