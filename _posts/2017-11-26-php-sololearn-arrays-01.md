---
layout: post
title: "01. 숫자 배열 (Arrays)"
categories: dev
tags: php
---

###### [SoloLearn](https://www.sololearn.com/) PHP 번역

<br>

# PHP Numeric Arrays

###### PHP 숫자 배열

------

<br>

<br>

## Arrays

###### 배열

- An array is a special variable, which can hold more than one value at a time.
  - 배열은 특별한 변수이다.
  - 한 번에 둘 이상의 값을 저장할 수 있다.
- If you have a list of items (a list of names, for example), storing them in single variables would look like this:
  - 항목 list를 하나의 변수에 저장하면 다음과 같다.

```php
$name1 = "David";
$name2 = "Amy";
$name3 = "John";
```

<br>

- But what if you have 100 names on your list?
  - 하지만 list에 100명의 이름이 있다면?
- The solution: Create an array!
  - 해답은 배열이다.

<br>

#### Numeric Arrays

###### 숫자 배열

<br>

- Numeric or indexed arrays associate a numeric index with their values.
  - 숫자 또는 인덱스 배열은 숫자 인덱스를 해당 값과 연결한다.
- The index can be assigned automatically (index always starts at `0`), like this:
  - 다음과 같이 인덱스를 자동으로(인덱스는 항상 `0`부터 시작한다) 할당할 수 있다.

```php
$names = array("David", "Amy", "John");
```

<br>

- As an alternative, you can assign your index manually.
  - 인덱스를 수동으로 할당할 수도 있다.

```php
$names[0] = "David";
$names[1] = "Amy";
$names[2] = "John";
```

<br>

- We defined an array called `$names` that stores three values.
  - 세 개의 값을 저장하는 `$names`라는 배열을 정의했다.
- You can access the array elements through their indices.
  - 인덱스를 통해 배열 element에 액세스할 수 있다.

```php
echo $names[1];	// "Amy"
```

<br>

> Remember that the first element in an array has the index of `0`, not 1.
>
> 배열에서 첫 번째 element는 인덱스가 1이 아닌 `0`이다.

<br>

<br>

- You can have integers, strings, and other data types together in one array.
  - 정수, 문자열, 다른 데이터 타입을 하나의 배열에서 가질 수 있다.

<br>

- Example:

```php
<?php
   $myArray[0] = "John";
	$myArray[1] = "<strong>PHP</strong>";
	$myArray[2] = 21;

	echo "$myArray[0] is $myArray[2] and knows $myArray[1]";
?>
   
// John is 21 and knows PHP
```

------

<br>

## QUIZ

- What is the index of the first element of the array?
  - 배열에서 첫 번째 element의 인덱스는 무엇인가?

> `0`

<br>

- Fill in the blanks to output "PHP is awesome" to the screen.
  - 화면에 "PHP is awesome"을 출력해라.

```php
<?php
   $arr[0] = 'PHP';
	$arr[1] = 'awesome';
	$arr[2] = ' is ';

	echo "$arr[0] $arr[2] $arr[1]";
?>
```

<br>