---
layout: post
title: "04. 변수 scope (Variables)"
categories: dev
tags: php
---

###### [SoloLearn](https://www.sololearn.com/) PHP 번역

<br>

# PHP Variable Scope

###### PHP 변수 scope

<br>

- PHP variables can be declared anywhere in the script.
  - PHP 변수는 스크립트의 어디에서나 선언할 수 있다.
- The `scope` of a variable is the part of the script in which the variable can be referenced or used.
  - 변수의 `scope`는 변수가 참조되거나, 사용될 수 있는 스크립트의 일부이다.

<br>

- PHP's most used variable scopes are `local`, `global`.
  - PHP에서 가장 많이 사용되는 변수 scope는 `loacl`과 `global`이다.
- A variable declared outside a function has a `global scope`.
  - 함수 외부에서 선언된 변수에는 `global scope`가 있다.
- A variable declared within a function has a `local scope`, and can only be accessed within that function.
  - 함수 내에서 선언된 변수는 `local scope`를 가지며, 함수 내에서만 액세스 할 수 있다.

<br>

- Consider the following example.
  - 다음 예제를 살펴보자.

```php
<?php
   $name = 'David';
	function getName() {
   	echo $name;
	}
	getName();

	// Error: Undefined variable: name
?>
```

[코드 실행 확인 링크](https://code.sololearn.com/488/#php)

<br>

- This script will produce an error, as the `$name` variable has a `global` scope, and is not accessible within the `getName()` function.
  - 이 스크립트는 `$name` 변수가 `global` scope를 가지며, `getName()` 함수 내에서 액세스 할 수 없으므로, 에러가 발생한다.

------

<br>

## The global Keyword

###### global 키워드

<br>

- The `global` keyword is used to access a global variable from within a function.
  - `global` 키워드는 함수 내에서 global 변수에 액세스 하는 데 사용된다.
- To do this, use the `global` keyword within the function, prior to the variables.
  - 이렇게 하려면, 함수 내에서 변수 앞에 `global` 키워드를 사용해라.

```php
<?php
   $name = 'David';
	function getName() {
   	global $name;
      echo $name;
	}
	getName();

	// Outputs 'David'
?>
```

[코드 실행 확인 링크](https://code.sololearn.com/467/#php)

------

<br>

## QUIZ

- In the example, why did we get a PHP error?
  - 이전 예제에서, 왜 PHP 에러가 발생했나?

> `The variable was not defined within the function`
>
> 함수 내에서 변수가 정의되지 않았다

<br>

- What output results from the following code?
  - 다음 코드의 결과는 무엇인가?

```php
<?php
   $num1 = 56;
	function my_func() {
   	$num1 = 89;
      echo $num1;
	}
	my_func();
?>
```

> `89`

<br>