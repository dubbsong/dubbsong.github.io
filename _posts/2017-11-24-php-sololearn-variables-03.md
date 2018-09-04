---
layout: post
title: "03. 데이터 타입 (Variables)"
categories: dev
tags: php
---

###### [SoloLearn](https://www.sololearn.com/) PHP 번역

<br>

# PHP Data Types

###### PHP 데이터 타입

<br>

- Variables can store a variety of data types.
  - 변수는 다양한 데이터 타입을 저장할 수 있다.
- Data types supported by PHP: `String`, `Integer`, `Float`, `Boolean`, `Array`, `Object`, NULL, Resource.
  - PHP에서 지원하는 데이터 타입이 있다.
  - `String`, `Integer`, `Float`, `Boolean`, `Array`, `Object`, NULL, Resource.

<br>

#### PHP String

###### PHP 문자열

<br>

- A string is a sequence of characters, like "Hello world!"
  - 문자열은 "Hello world!"와 같은 일련의 문자이다.
- A string can be any text within a set of single or double `quotes`.
  - 문자열은 작은따옴표나 큰따옴표로 묶인 텍스트일 수 있다.

```php
<?php
   $string1 = "Hello world!";	// double quotes
	$string2 = 'Hello world!';	// single quotes
?>
```

<br>

> You can join two strings together using the dot (.) concatenation operator.
>
> 점(.) 연결 연산자를 사용해서 두 문자열을 결합할 수 있다.

> For example: `echo $s1. $s2`

<br>

#### PHP Integer

###### PHP 정수

<br>

- An integer is a whole number (without decimals) that must fit the following criteria:
  - 정수는 다음 기준에 맞아야 하는 정수(소수가 없는)이다.

> It cannot contain commas or blanks
>
> 쉼표나 공백을 포함할 수 없다

> It must not have a decimal point
>
> 소수점을 가질 수 없다

> It can be either positive or negative
>
> 양수나 음수가 될 수 있다

```php
<?php
   $int1 = 42;	// positive number
	$int2 = -42;	// negative number
?>
```

------

<br>

## PHP Float

###### PHP 부동 소수점

<br>

- A float, or floating point number, is a number that includes a decimal point.
  - 부동 소수점 숫자는 소수점을 포함하는 숫자이다.

```php
<?php
   $x = 42.168;
?>
```

<br>

#### PHP Boolean

###### PHP Boolean

<br>

- A `Boolean` represents two possible states: TRUE or FALSE.
  - `Boolean`은 TRUE 또는 FALSE 두 가지의 상태를 나타낸다.

```php
<?php
   $x = true; $y = false;
?>
```

<br>

> Booleans are often used in conditional testing, which will be covered later on in the course.
>
> Boolean은 종종 조건 테스트에 사용되며, 나중에 다룰 예정이다.

<br>

- Most of the data types can be used in combination with one another.
  - 대부분의 데이터 타입은 서로 조합해서 사용할 수 있다.
- In the example, string and integer are put together to determine the sum of two numbers.
  - 아래 예제에서, 문자열과 정수는 함께 두 숫자의 합을 결정한다.

```php
<?php
   $str = "10";
	$int = 20;
	$sum = $str + $int;
	echo ($sum);

	// Output 30
?>
```

[코드 실행 확인 링크](https://code.sololearn.com/465/#php)

<br>

> PHP automatically converts each variable to the correct data type, according to its value.
>
> PHP는 값에 따라 각 변수를 올바른 데이터 타입으로 자동 변환한다.

> This is why the variable `$str` is treated as a number in the addition.
>
> 변수 `$str`이 숫자로 취급되는 이유이다.

------

<br>

## QUIZ

- Fill in the blank to define the variable string:
  - 변수 문자열을 정의해라.

```php
<?php
   $string = "I am learning PHP";
?>
```

<br>

- What output results from the following code?
  - 다음 코드의 결과는 무엇인가?

```php
<?php
   $someString = "15";
	$birthyear = 1982;
	echo $someString + $birthyear;
?>
```

> `1997`

<br>