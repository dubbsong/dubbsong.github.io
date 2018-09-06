---
layout: post
title: "03. 다차원 배열 (Arrays)"
categories: dev
tags: php
---

###### [SoloLearn](https://www.sololearn.com/) PHP 번역

<br>

# PHP Multi-Dimensional Arrays

###### PHP 다차원 배열

<br>

- A `multi-dimensional` array contains one or more arrays.
  - `다차원` 배열은 하나 이상의 배열을 포함한다.

<br>

- The dimension of an array indicates the number of indices you would need to select an element.
  - 배열의 다차원은 element를 선택하는 데 필요한 인덱스의 수를 나타낸다.
- For a `two-dimensional` array, you need two indices to select an element.
  - `2차원` 배열의 경우, element를 선택하기 위해 두 개의 인덱스가 필요하다.
- For a `three-dimensional` array, you need three indices to select an element.
  - `3차원` 배열의 경우, element를 선택하기 위해 세 개의 인덱스가 필요하다.

<br>

> Arrays more than three levels deep are difficult to manage.
>
> 3단계 이상의 깊은 배열은 관리하기가 어렵다.

<br>

<br>

- Let's create a two-dimensional array that contains 3 arrays:
  - 3개의 배열을 포함하는 2차원 배열을 만들어보자.

```php
$people = array(
   'online' => array('David', 'Amy'),
   'offline' => array('John', 'Rob', 'Jack'),
   'away' => array('Arthur', 'Daniel')
);
```

<br>

- Now the two-dimensional `$people` array contains 3 arrays, and it has two indices: `row` and `column`.
  - 이제 2차원 `$people` 배열에는 3개의 배열이 포함되며, `row`와 `column`이라는 두 개의 인덱스가 있다.
- To access the elements of the \$people array, we must point to the two indices.
  - \$people 배열의 element에 액세스하려면, 두 개의 인덱스를 가리켜야 한다.

```php
echo $people['online'][0];	// David
echo $people['away'][1];	// Daniel
```

[코드 실행 확인 링크](https://code.sololearn.com/475/#php)

<br>

> The arrays in the multi-dimensional array can be both numeric and associative.
>
> 다차원 배열에서 배열은 숫자와 연결 모두 가질 수 있다.

------

<br>

## QUIZ

- How many dimensions are possible in a multi-dimensional array?
  - 다차원 배열에서 가능한 차원은 몇 개인가?

> `As many as you want`

<br>

- Fill in the blanks to declare a two-dimensional array.
  - 2차원 배열을 선언해라.

```php
<?php
   $cars = array(
		'BMW' => array('X5', 'red', '2013'),
   	'AUDI' => array('A4', 'white', '2008')
	);
?>
```

<br>