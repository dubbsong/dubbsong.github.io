---
layout: post
title: "02. 데이터 타입 (Basic Concepts)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript Data Types

###### JavaScript 데이터 타입

<br>

- The term `data type` refers to the types of values with which a program can work.
  - `데이터 타입`이라는 용어는 프로그램이 작동할 수 있는 값의 타입을 나타낸다.
- JavaScript variables can hold many data types, such as `numbers`, `strings`, `arrays`, and more.
  - JavaScript 변수는 `숫자`, `문자열`, `배열` 등과 같은 많은 데이터 타입을 포함할 수 있다.

<br>

- Unlike many other programming languages, JavaScript does not define different types of numbers, like integers, short, long, floating-point, etc.
  - 많은 다른 프로그래밍 언어와 달리, JavaScript는 정수, 짧은, 긴, 부동 소수점 등의 다른 타입의 숫자를 정의하지 않는다.

<br>

- JavaScript numbers can be written with or without decimals.
  - JavaScript 숫자는 10진수의 유무와 상관없이 작성할 수 있다.

```js
var num = 42;	// A number without decimals
```

------

<br>

## Floating-Point Numbers

###### 부동 소수점 숫자

<br>

- JavaScript numbers can also have decimals.
  - JavaScript 숫자는 소수도 가질 수 있다.

```html
<script>
	var price = 55.55;
   document.write(price);
</script>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-js-basic concepts-02-01.png)

<br>

> JavaScript numbers are always stored as `double precision floating point numbers`.
>
> JavaScript 숫자는 항상 `배정밀도 부동 소수점 숫자`로 저장된다.

------

<br>

## Strings

###### 문자열

<br>

- JavaScript `strings` are used for storing and manipulating text.
  - JavaScript `문자열`은 텍스트 저장과 조작에 사용된다.
- A string can be any text that appears within `quotes`.
  - 문자열은 `따옴표` 내에 표시되는 텍스트이다.
- You can use single or double quotes.
  - 작은 따옴표나 큰 따옴표를 사용할 수 있다.

```js
var name = 'John';
var text = "My name is John Smith";
```

<br>

- You can use quotes inside a string, as long as they don't match the quotes surrounding the string.
  - 문자열을 둘러싼 따옴표와 일치하지 않는 한, 문자열 내에서 따옴표를 사용할 수 있다.

```js
var text = "My name is 'John'";
```

<br>

<br>

- As strings must be written within quotes, quotes inside the string must be handled.
  - 문자열은 따옴표 내에 작성해야 하므로, 문자열 내의 따옴표를 처리해야 한다.
- The `backslash(\) escape character` turns special characters into string characters.
  - `백 슬래시(\) 이스케이프 문자`는 특수 문자를 문자열 문자로 변환한다.

```js
var sayHello = 'Hello world!\'I am a JavaScript programmer.\'';
document.write(sayHello);
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-js-basic concepts-02-02.png)

<br>

- The escape character(\\) can also be used to insert other special characters into a string.
  - 이스케이프 문자(\\)를 사용해서 다른 특수 문자열를 문자열에 삽입할 수도 있다.
- These special characters can be added to a text string using the backslash sign.
  - 이러한 특수 문자는 백 슬래시 기호를 사용해서 텍스트 문자열에 추가할 수 있다.

![sololearn img](/assets/img/sololearn-js-basic concepts-02-03.png)

<br>

> If you begin a string with a single quote, then you should also end it with a single quote.
>
> 작은 따옴표로 문자열을 시작한다면, 작은 따옴표로 끝내야 한다.

------

<br>

## Booleans

###### Boolean(불리언)

<br>

- In JavaScript Boolean, you can have one of two values, either `true` or `false`.
  - JavaScript Boolean에서는, `true` 또는 `false`의 두 값 중 하나를 사용할 수 있다.
- These are useful when you need a data type that can only have one of two values, such as Yes/No, On/Off, True/False.
  - Yes/No, On/Off, True/False와 같은 두 가지 값 중 하나만 가질 수 있는 데이터 타입이 필요할 때 유용하다.

<br>

- Example:

```js
var isActive = true;
var isHoliday = false;
```

<br>

> The Boolean value of 0 (zero), null, undefined, empty string is `false`.
>
> 0, null, undefined, 빈 문자열의 Boolean 값은 `false`이다.

> Everything with a "real" value is `true`.
>
> "진짜" 값을 가진 모든 것은 `true`이다.

------

<br>

## QUIZ

- Fill in the blanks to declare a variable age and assign it the number 18:
  - 변수 age를 선언하고, 숫자 18을 할당해라.

```js
var age = 18;
```

<br>

- A floating point number:
  - 부동 소수점 숫자는:

> `is allowed to have a decimal place`
>
> 소수 자리수를 허용한다.

<br>

- In order to create a string, we need to put the text inside...
  - 문자열을 만들려면, ...내에 텍스트를 넣어야 한다.

> `Quotation marks` (따옴표)

<br>

- Please enter the corresponding characters to enable the display of the whole string:
  - 전체 문자열을 표시하려면, 해당 문자를 입력해라.

```js
var s = "I think
\"JavaScript is
easy\"";

document.write(s);
```

<br>

- What two values does the Boolean data type accept?
  - Boolean 데이터 타입은 어떤 두 가지 값을 허용하는가?

> `true` and `false`

<br>