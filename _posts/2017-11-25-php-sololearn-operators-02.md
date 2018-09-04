---
layout: post
title: "02. 할당 연산자 (Operators)"
categories: dev
tags: php
---

###### [SoloLearn](https://www.sololearn.com/) PHP 번역

<br>

# PHP Assignment Operators

###### PHP 할당 연산자

<br>

- `Assignment` operators are used to write values to variables.
  - `할당` 연산자는 변수에 값을 작성하는 데 사용된다.

```php
$num1 = 5;
$num2 = $num1;
```

<br>

- `$num1` and `$num2` now contain the value of 5.
  - `$num1`과 `$num2`에는 이제 5의 값이 포함된다.

<br>

- Assignments can also be used in conjunction with arithmetic operators.
  - 할당 연산자는 산술 연산자와 함께 사용할 수도 있다.

![sololearn img](/assets/img/sololearn-php-operators-02-01.png)

<br>

- Example:

```php
<?php
   $x = 50;
	$x += 100;
	echo $x;	// 150
?>
```

------

<br>

## QUIZ

- What output results from the following code?
  - 다음 코드의 결과는 무엇인가?

```php
<?php
   $a = 7; $b = 3;
	$a += $b;
	echo $a;
?>
```

> `10`

<br>