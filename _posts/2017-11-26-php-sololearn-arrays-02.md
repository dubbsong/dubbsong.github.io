---
layout: post
title: "02. 연결 배열 (Arrays)"
categories: dev
tags: php
---

###### [SoloLearn](https://www.sololearn.com/) PHP 번역

<br>

# PHP Associative Arrays

###### PHP 연결 배열

<br>

- `Associative` arrays are arrays that use named keys that you assign to them.
  - `연결` 배열은 할당한 명명된 key를 사용하는 배열이다.
- There are two ways to create an associative array:
  - 연결 배열을 만드는 데에는 두 가지 방법이 있다.

```php
$people = array("David" => "27", "Amy" => "21", "John" => "42");
```

```php
$people['David'] = "27";
$people['Amy'] = "21";
$people['John'] = "42";
```

<br>

> In the first example, note the use of the => signs in assigning values to the named keys.
>
> 첫 번째 예제에서는, 명명된 key에 값을 할당할 때 => 기호를 사용한다.

<br>

<br>

- Use the named keys to access the array's members.
  - 배열의 항목에 액세스하려면, 명명된 key를 사용해라.

```php
$people = array("David" => "27", "Amy" => "21", "John" => "42");

echo $people['Amy'];	// 21
```

[코드 실행 확인 링크](https://code.sololearn.com/474/#php)

------

<br>

## QUIZ

- Which syntax corresponds to the associative array?
  - 연결 배열에 해당하는 구문은 무엇인가?

> `'key' => value`

<br>

- Fill in the blanks to output the age from the array.
  - 배열에서 age를 출력해라.

```php
<?php
   $man = array("name" => "John", "age" => 25");
	echo $man['age'];
?>
```

<br>