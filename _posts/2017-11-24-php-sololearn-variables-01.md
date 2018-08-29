---
layout: post
title: "01. 변수 (Variables)"
categories: dev
tags: php
---

###### [SoloLearn](https://www.sololearn.com/) PHP 번역

<br>

# PHP Variables

###### PHP 변수

<br>

- `Variables` are used as "containers" in which we store information.
  - `변수`는 정보를 저장하는 "컨테이너"로 사용된다.
- A PHP variable starts with a dollar sign ($), which is followed by the name of the variable.
  - PHP 변수는 달러 기호($)로 시작하며, 그 뒤에 변수 이름이 온다.

```php
$variable_name = value;
```

<br>

#### Rules for PHP variables:

###### PHP 변수 규칙:

<br>

> A variable name must start with a letter or an underscore
>
> 변수 이름은 문자 또는 밑줄로 시작해야 한다

> A variable name cannot start with a number
>
> 변수 이름은 숫자로 시작할 수 없다

> A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _)
>
> 변수 이름에는 영숫자 문자와 밑줄만 포함할 수 있다 (A-z, 0-9, _)

> Variable names are case-sensitive (\$name and \$NAME would be two different variables)
>
> 변수 이름은 대소문자를 구분한다 (\$name과 \$NAME은 두 개의 다른 변수가 된다)

<br>

- For example:

```php
<?php
   $name = 'John';
	$age = 25;
	echo $name;

	// Outputs 'John'
?>
```

[코드 실행 확인 링크](https://code.sololearn.com/462/#php)

<br>

- In the example above, notice that we did not have to tell PHP which data type the variable is.
  - 위의 예제에서, 변수가 어떤 데이터 타입을 PHP에 알릴 필요가 없음에 주목해라.
- PHP automatically converts the variable to the correct data type, depending on its value.
  - PHP는 값에 따라 올바른 데이터 타입으로 자동 변환한다.

<br>

> Unlike other programming languages, PHP has no command for declaring a variable.
>
> 다른 프로그래밍 언어와 달리, PHP는 변수 선언을 위한 명령이 없다.

> It is created the moment you first assign a value to it.
>
> 처음에 값을 할당하는 순간 생성된다.

------

<br>

## QUIZ

- Fill in the blanks to declare the variables \$name and \$age and assign their values.
  - \$name과 \$age 변수를 선언하고, 값을 할당해라.

```php
<?php
   $name = "David";
	$age = 25;
?>
```

<br>