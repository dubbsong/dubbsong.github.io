---
layout: post
title: "01. if else 문 (Control Structures)"
categories: dev
tags: php
---

###### [SoloLearn](https://www.sololearn.com/) PHP 번역

<br>

# PHP if else statement

###### PHP if else 문

------

<br>

<br>

## Conditional Statements

###### 조건문

<br>

- `Conditional statements` perform different actions for different decisions.
  - `조건문`은 다른 결정에 대해 다른 동작을 수행한다.
- The `if else` statement is used to execute a certain code if a condition is `true`, and another code if the condition is `false`.
  - `if else` 문은 조건이 `true`인 경우 특정 코드를 실행하고, 조건이 `false`인 경우 다른 코드를 실행하는 데 사용된다.

<br>

- Syntax:

```php
if (condition) {
   code to be executed if condition is true;
} else {
   code to be executed if condition is false;
}
```

<br>

> You can also use the `if` statement without the `else` statement, if you do not need to do anything, in case the condition is `false`.
>
> 조건이 `false`인 경우에 대비해서, `else` 문 없이 `if` 문을 사용할 수도 있다.

------

<br>

## if else

- The example below will output the greatest number of the two.
  - 아래 예제는 둘 중 가장 큰 수를 출력한다.

```php
<?php
   $x = 10;
	$y = 20;

	if ($x >= $y) {
   	echo $x;
	} else {
   	echo $y;
	}
?>
   
// 20
```

[코드 실행 확인 링크](https://code.sololearn.com/476/#php)

------

<br>

## QUIZ

- Fill in the blanks to output "Welcome", if the variable 'age' is greater than 18.
  - 변수 'age'가 18보다 큰 경우, "Welcome"을 출력해라.

```php
if ($age > 18) {
   echo "Welcome";
}
```

<br>

- Drag and drop from the options below to print "YES" if the variable 'num' is equal to 100, "NO" if it is not.
  - 변수 'num'이 100이면 "YES"를, 그렇지 않으면 "NO"를 출력해라.

```php
if ($num == 100) {
   echo "YES";
} else {
   echo "NO";
}
```

<br>