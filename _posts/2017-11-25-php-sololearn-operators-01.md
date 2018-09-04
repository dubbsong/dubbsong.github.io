---
layout: post
title: "01. 산술 연산자 (Operators)"
categories: dev
tags: php
---

###### [SoloLearn](https://www.sololearn.com/) PHP 번역

<br>

# PHP Arithmetic Operators

###### PHP 산술 연산자

------

<br>

<br>

## Operators

###### 연산자

<br>

- `Operaters` carry out operations on variables and values.
  - `연산자`는 변수와 값에 대한 연산을 수행한다.

![sololearn img](/assets/img/sololearn-php-operators-01-01.png)

<br>

#### Arithmetic Operators

###### 산술 연산자

<br>

- Arithmetic operators work with numeric value to perform common arithmetical operations.
  - 산술 연산자는 숫자 값을 사용해서 일반적인 산술 연산을 수행한다.

![sololearn img](/assets/img/sololearn-php-operators-01-02.png)

<br>

- Example:

```php
<?php
   $num1 = 8;
	$num2 = 6;

	// 덧셈
	echo $num1 + $num2;	// 14

	// 뺄셈
	echo $num1 - $num2;	// 2

	// 곱셈
	echo $num1 * $num2;	// 48

	// 나눗셈
	echo $num1 / $num2;	// 1.33333333333
?>
```

------

<br>

## Modulus

- The `modulus` operator, represented by the % sign, returns the remainder of the division of the first operand by the second operand:
  - % 기호로 나타내는 `modulus` 연산자는, 두 번째 피연산자로 첫 번째 피연산자를 나눈 나머지를 반환한다.

```php
<?php
   $x = 14;
	$y = 3;
	echo $x % $y;	// 2
?>
```

<br>

> If you use floating point numbers with the modulus operator, they will be converted to `integers` before the operation.
>
> modulus 연산자에 부동 소수점 숫자를 사용하면, 연산 전에 `정수`로 변환된다.

------

<br>

## Increment & Decrement

###### 증가 & 감소

<br>

- The `increment` operators are used to increment a variable's value.
  - `증가` 연산자는 변수의 값을 증가시키는 데 사용된다.
- The `decrement` operators are used to decrement a variable's value.
  - `감소` 연산자는 변수의 값을 감소시키는 데 사용된다.

```php
$x++;	// $x = $x + 1;
$x--;	// $x = $x - 1;
```

<br>

- Increment and decrement operators either precede or follow a variable.
  - 증가와 감소 연산자는 변수 앞 또는 뒤에 온다.

```php
$x++;	// 이후 증가
$x--;	// 이후 감소
++$x;	// 사전 증가
--$x;	// 사전 감소
```

<br>

- The difference is that the post-increment returns the original value `before` it changes the variable, while the pre-increment changes the variable first and then returns the value.
  - 차이점은, 이후 증가는 변수를 변경하기 전에 원래 값을 반환하고, 사전 증가는 변수를 먼저 변경한 다음 값을 반환한다는 것이다.

<br>

- Example:

```php
$a = 2; $b = $a++;	// $a = 3, $b = 2
$a = 2; $b = ==$a;	// $a = 3, $b = 3
```

<br>

> The increment operators are used to increment a variable's value.
>
> 증가 연산자는 변수의 값을 증가시키는 데 사용된다.

------

<br>

## QUIZ

- Fill in the blanks to subtract one number from the other.
  - 하나의 숫자를 다른 숫자에서 빼라.

```php
<?php
   $num1 = 23;
	$num2 = 16;
	echo $num1 - $num2;
?>
```

<br>

- What would the value of the variable $num be after the following code?
  - 변수 $num의 값은 다음 코드 후에 무엇이 되는가?

```php
<?php
   $num = 9;
	$num = $num % 2;
?>
```

> `1`

<br>

- What output results from the following code?
  - 다음 코드의 결과는 무엇인가?

```php
<?php
   $num = 18;
	$num--;
	echo $num;
?>
```

> `17`

<br>