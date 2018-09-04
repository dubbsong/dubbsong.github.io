---
layout: post
title: "05. $$ (Variables)"
categories: dev
tags: php
---

###### [SoloLearn](https://www.sololearn.com/) PHP 번역

<br>

- With PHP, you can use one variable to specify another variable's name.
  - PHP를 사용하면, 하나의 변수를 사용해서 다른 변수의 이름을 지정할 수 있다.
- So, a `variable variable` treats the value of another variable as its name.
  - 따라서, `variable variable`은 다른 변수의 값을 그 이름으로 간주한다.

<br>

- For example:

```php
<?php
   $a = 'hello';
	$hello = "Hi!";
	echo $$a;
?>

// Hi!
```

[코드 실행 확인 링크](https://code.sololearn.com/468/#php)

<br>

> `$$a` is a variable that is using the value of another variable, `$a`, as its name.
>
> `$$a`는 다른 변수 `$a`의 값을 이름으로 사용하는 변수이다.

> The value of `$a` is equal to "hello".
>
> `$a`의 값은 "hello"와 같다.

> The resulting variable is `$hello`, which holds the value "Hi!".
>
> 결과 변수는 `$hello`이며, "Hi!" 값을 보유한다.

------

<br>

## QUIZ

- Fill in the blank to print "World" to the screen.
  - "World"를 화면에 출력해라.

```php
<?php
   $Hello = "World";
	$a = "Hello";
	echo $$a;
?>
```

<br>