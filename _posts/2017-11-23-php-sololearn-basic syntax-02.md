---
layout: post
title: "02. PHP 태그 (Basic Syntax)"
categories: dev
tags: php
---

###### [SoloLearn](https://www.sololearn.com/) PHP 번역

<br>

# PHP Tags

###### PHP 태그

------

<br>

<br>

## PHP Syntax

###### PHP 문법

<br>

- A PHP script starts with `<?php` and ends with `?>`:
  - PHP 스크립트는 `<?php`로 시작하고, `?>`로 끝난다.

```php+HTML
<?php
	// PHP code goes here
?>
```



<br>

- Here is an example of a simple PHP file.
  - 다음은 간단한 PHP 파일의 예제이다.
- The PHP script uses a built in function called "echo" to output the text "Hello World!" to a webpage.
  - PHP 스크립트는 "echo"라는 내장 함수를 사용해서 "Hello World!" 텍스트를 웹페이지에 출력한다.

```php+HTML
<html>
   <head>
      <title>My First PHP Page</title>
   </head>
   <body>
      <?php
      	echo "Hello World!";
      ?>
   </body>
</html>
```

[코드 실행 확인 링크](https://code.sololearn.com/454/#php)

<br>

> PHP statements end with `semicolons(;)`.
>
> PHP 문은 `세미콜론(;)`으로 끝난다.

<br>

<br>

- Alternatively, we can include PHP in the HTML `<script>` tag.
  - 또는, HTML `<script>` 태그에 PHP를 포함할 수 있다.

```php+HTML
<html>
   <head>
      <title>My First Page</title>
   </head>
   <body>
      <script language="php">
      	echo "Hello World!";
      </script>
   </body>
</html>
```

<br>

> However, the latest version of PHP removes support for \<script language="php"> tags.
>
> 하지만, 최신 버전의 PHP는 \<script language="php"> 태그에 대한 지원을 제거했다.

> As such, we recommend using `<?php ?>` exclusively.
>
> 따라서, `<?php ?>`만 사용하는 것이 좋다.

<br>

<br>

- You can also use the shorthand PHP tags, \<? ?>, as long as they're supported by the server.
  - 서버가 지원하는 한, 약식 PHP 태그인 \<? ?>를 사용할 수도 있다.

```php+HTML
<?
	echo "Hello World!";
?>
```

[코드 실행 확인 링크](https://code.sololearn.com/456/#php)

<br>

> However, `<?php ?>`, as the official standard, is the recommended way of defining PHP scripts.
>
> 하지만, `<?php ?>`는 PHP 스크립트를 정의하는 데 권장되는 공식 표준이다.

------

<br>

## QUIZ

- Fill in the correct character.
  - 올바른 문자를 입력해라.

```php+HTML
<?php
	echo 'Hello';
?>
```

<br>

- Which of the following is correct when using PHP with the script tag?
  - 스크립트 태그와 함께 PHP를 사용할 때 올바른 것은 무엇인가?

> [ ] \<script type="text/javascript">
>
> [ ] \<script type="application/ecmascript">
>
> [ ] `<script language="php">`

<br>

- Which is the most widely recommended way to use PHP tags?
  - PHP 태그를 사용하는 가장 널리 권장되는 것은 무엇인가?

> `<?php`

<br>
