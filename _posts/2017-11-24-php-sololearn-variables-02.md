---
layout: post
title: "02. 상수(Constants) (Variables)"
categories: dev
tags: php
---

###### [SoloLearn](https://www.sololearn.com/) PHP 번역

<br>

# PHP Constants

###### PHP 상수

<br>

- `constants` are similar to variables except that they cannot be changed or undefined after they've been defined.
  - `상수`는 정의된 후에 변경하거나, 정의할 수 없다는 점을 제외하고는 변수와 비슷하다.
- Begin the name of your constant with a letter or an underscore.
  - 문자나 밑줄로 상수 이름을 시작해라.
- To create a constant, use the `define()` function:
  - 상수를 만들려면, `define()` 함수를 사용해라.

```php
define(name, value, case-insensitive)
```

<br>

#### Parameters:

- `name`: Specifies the name of the constant;
  - 상수의 이름을 지정한다.
- `value`: Specifies the value of the constant;
  - 상수의 값을 지정한다.
- `case-insensitive`: Specifies whether the constant name should be case-insensitive. Default is `false`;
  - 상수 이름이 대소문자를 구분해야 하는지를 지정한다. 기본값은 `false`이다.

<br>

- The example below creates a constant with a `case-sensitive` name:
  - 아래 예제에서는, `대소문자를 구분하는` 이름을 가진 상수를 생성한다.

```php
<?php
   define("MSG", "Hi SoloLearners!");
	echo MSG;

	// Outputs "Hi SoloLearners!"
?>
```

[코드 실행 확인 링크](https://code.sololearn.com/463/#php)

<br>

- The example below creates a constant with a `case-insensitive` name:
  - 아래 예제에서는, `대소문자를 구분하지 않는` 이름을 가진 상수를 생성한다.

```php
<?
   define("MSG", "Hi SoloLearners!", true);
	echo msg;

	// Outputs "Hi SoloLearners!"
?>
```

[코드 실행 확인 링크](https://code.sololearn.com/464/#php)

<br>

> No dollar sign ($) is necessary before the constant name.
>
> 상수 이름 앞에는 달러 기호($)가 필요하지 않다.

------

<br>

## QUIZ

- Fill in the blanks to declare a case-sensitive constant called AGE and assign the value 28 to it.
  - AGE라는 대소문자를 구분하는 상수를 선언하고, 값 28을 할당해라.

```php
<?php
   define("AGE", 28);
?>
```

<br>