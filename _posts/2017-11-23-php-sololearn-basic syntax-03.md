---
layout: post
title: "03. echo 함수 (Basic Syntax)"
categories: dev
tags: php
---

###### [SoloLearn](https://www.sololearn.com/) PHP 번역

<br>

# PHP Echo

###### PHP echo 함수

<br>

- PHP has a built-in "echo" function, which is used to output text.
  - PHP에는 텍스트를 출력하는 데 사용되는 내장 "echo" 함수가 있다.
- In actuality, it's not a function; it's a `language construct`.
  - 사실 "echo" 함수는 함수가 아니고, `언어 구조`이다.
- As such, it does not require parentheses.
  - 따라서, 괄호는 필요하지 않다.

<br>

- Let's output a text.
  - 텍스트를 출력해보자.

```php
<?php
   echo "I love PHP!";
?>
```

[코드 실행 확인 링크](https://code.sololearn.com/457/#php)

<br>

> The text should be in single or double `quotation marks`.
>
> 텍스트는 작은 따옴표나 큰 따옴표로 묶어야 한다.

------

<br>

## PHP Statements

###### PHP 문

<br>

- Each PHP statement must end with a `semicolon`.
  - 각 PHP 문은 `세미콜론`으로 끝나야 한다.

```php
<?php
   echo "A";
	echo "B";
	echo "C";
?>
```

[코드 실행 확인 링크](https://code.sololearn.com/458/#php)

<br>

> Forgetting to add a semicolon at the end of a statement results in an `error`.
>
> 명령문 뒤에 세미콜론 추가를 잊어버리면, `에러`가 발생한다.

------

<br>

## Echo

###### echo 함수

<br>

- HTML markup can be added to the text in the echo statement.
  - echo 문에서 텍스트에 HTML 마크업을 추가할 수 있다.

```php
<?php
   echo "<strong>This is a bold text.</strong>";
?>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-php-basic syntax-03-01.png)

------

<br>

## QUIZ

- Fill in the blanks to output "Hi" using echo:
  - echo를 사용해서 "Hi"를 출력해라.

```php+HTML
<?php
	echo "Hi";
?>
```

<br>

- Which character has to be at the end of each statement?
  - 어떤 문자가 각 명령문의 끝에 있어야 하는가?

> `;`

<br>

- Fill in the blanks to output "SoloLearn" as a h1 heading:
  - "SoloLearn"을 h1 heading으로 출력해라.

```php
<?php
   echo "<h1>SoloLearn</h1>";
?>
```

<br>