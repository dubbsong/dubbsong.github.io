---
layout: post
title: "04. 주석 (Basic Syntax)"
categories: dev
tags: php
---

###### [SoloLearn](https://www.sololearn.com/) PHP 번역

<br>

# PHP Comments

###### PHP 주석

<br>

- In PHP code, a `comment` is a line that is not executed as part of the program.
  - PHP 코드에서, `주석`은 프로그램의 일부로 실행되지 않는 줄이다.
- You can use comments to communicate to others so they understand what you're doing, or as a reminder to yourself of what you did.
  - 주석을 사용해서 다른 사람들과 소통할 수 있으므로, 당신이 하는 일을 상대방이 이해하거나, 자신이 한 일에 대해 상기시켜준다.

<br>

- A `single-line` comment starts with //:
  - `한 줄` 주석은 //로 시작한다.

```php
<?php
   echo "<p>Hello World!</p>";
	// This is a single-line comment
	echo "<p>I am learning PHP!</p>";
	echo "<p>This is my first program!</p>";
?>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-php-basic syntax-04-01.png)

------

<br>

## Multi-Line Comments

###### 여러 줄 주석

<br>

- `Multi-line` comments are used for composing comments that take more than a single line.
  - `여러 줄` 주석은 두 줄 이상의 주석을 작성하는 데 사용된다.
- A multi-line comment begins with /* and ends with */.
  - 여러 줄 주석은 /*로 시작하고, */로 끝난다.

```php
<?php
   echo "<p>Hello World!</p>";
	/*
	This is a multi-line comment block
	that spans over
	multiple lines
	*/
	echo "<p>I am learning PHP!</p>";
	echo "<p>This is my first program!</p>";
?>
```

[코드 실행 확인 링크](https://code.sololearn.com/461/#php)

<br>

> Adding comments as you write your code is a good practice.
>
> 코드를 작성할 때 주석을 추가하는 것이 좋다.

> It helps others understand your thinking and makes it easier for you to recall your thought processes when you refer to your code later on.
>
> 다른 사람들이 당신의 생각을 이해할 수 있게 도와주고, 나중에 코드를 참조할 때 생각 프로세스를 더 쉽게 기억할 수 있게 해준다.

------

<br>

## QUIZ

- Which of the following characters indicates comments in PHP?
  - PHP에서 주석을 나타내는 문자는 무엇인가?

> `//`

<br>

- Fill in the blanks to make the text a comment.
  - 텍스트를 주석으로 만들어라.

```php
/* Name: John
	Age: 24
	Date: 05/06/2014
/*
```

<br>