---
layout: post
title: "validatePIN.js (7kyu)"
categories: codewars
tags: Algorithm Codewars
---

#### 조건문(if) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

ATM machines allow 4 or 6 digit PIN codes

and PIN codes cannot contain anything

but exactly 4 digits or exactly 6 digits.

<br>

If the function is passed a valid PIN string,

return true, else return false.

<br>

## solution 01

```javascript
function validatePIN(pin) {
   const correctLength = (pin.length === 4 || pin.length === 6);
   const onlyNumber = pin.match(/^\d+$/);
   
   if (correctLength && onlyNumber) {
      return true;
   } else {
      return false;
   }
}


validatePIN('1234');	// true
validatePIN('a234');	// false
validatePIN('12345');	// false
validatePIN('123456');	// true
```

> 정규표현식 (RegExp)
>
> `match`: 정보를 가지고 있는 배열을 반환하거나 일치하지 않는 부분을 null로 반환한다.
>
> `^`: 입력의 시작에 일치한다.
>
> `$`: 입력의 끝에 일치한다.
>
> `\d`: 숫자 문자에 일치한다. (= `[0-9]`)
>
> `+`: 1회 이상 연속으로 반복되는 앞선 문자에 일치한다.

<br>

## solution 02

```javascript
function validatePIN(pin) {
   return /^(\d{4}|\d{6})$/.test(pin);
}


validatePIN('1234');	// true
validatePIN('a234');	// false
validatePIN('12345');	// false
validatePIN('123456');	// true
```

> 정규표현식 (RegExp)
>
> `test`: 일치하는 문자열을 검사하고 true나 false를 반환한다.
>
> `{n}`: 앞 문자가 n번 나타날 경우에 일치한다.
>
> `x|y`: x 또는 y에 일치한다.

<br>

## solution 03

```javascript
const validatePIN = pin => /^(\d{4}|\d{6})$/.test(pin);


validatePIN('1234');	// true
validatePIN('a234');	// false
validatePIN('12345');	// false
validatePIN('123456');	// true
```

<br>

## solution 04

```javascript
function validatePIN(pin) {
   return (pin.length === 4 || pin.length === 6) && parseInt(pin) == pin;
}


validatePIN('1234');	// true
validatePIN('a234');	// false
validatePIN('12345');	// false
validatePIN('123456');	// true
```

> 이해 필요 (== 연산자만 통과 가능)

<br>