---
layout: post
title: "(Filtering, Function, Subquery 04) 사용자 정의 column"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

## The CONCAT Function

###### CONCAT 함수

<br>

- The `CONCAT` function is used to concatenate two or more text values and returns the concatenating string.
  - `CONCAT` 함수는 두 개 이상의 텍스트 값을 연결하는 데 사용된다.
  - 그리고 연결된 문자열(string)을 반환한다.

<br>

- Let's concatenate the *FirstName* with the *City*, separating them with a *comma*:
  - *FirstName*과 *City*를 *쉼표*로 구분해서 연결해보자.

```mysql
SELECT CONCAT(FirstName, ',', City) FROM customers;
```

<br>

- The output result is:
  - 출력 결과는 다음과 같다.

![img](/assets/img/sql-sololearn-filtering&function&subquery-04-01.png)

<br>

> The CONCAT() function takes two or more parameters.
>
> CONCAT() 함수는 두 개 이상의 매개변수를 사용한다.

------

<br>

## The AS Keyword

###### AS 키워드

<br>

- A concatenation results in a new column.
  - 연결하면 새로운 column이 생성된다.
- The default column name will be the `CONCAT` function.
  - 기본 column 이름은 `CONCAT` 함수이다.
- You can assign a custom name to the resulting column using the `AS` keyword:
  - `AS` 키워드를 사용해서 결과 column에 사용자 정의 이름을 지정할 수 있다.

```mysql
SELECT CONCAT(FirstName, ',', City) AS new_column
FROM customers;
```

<br>

- And when you run the query, the column name appears to be changed.
  - query를 실행하면 column 이름이 변경된 것처럼 보인다.

![img](/assets/img/sql-sololearn-filtering&function&subquery-04-02.png)

<br>

> A concatenation results in a new column.
>
> 연결하면 새로운 column이 생성된다.

------

<br>

## Arithmetic Operators

###### 산술 연산자

<br>

- Arithmetic operators perform arithmetical operations on numeric operands.
  - 산술 연산자는 숫자 피연산자에 대해 산술 연산을 수행한다.
- The Arithmetic operators include addition (+), subtraction (-), multiplication (*) and division (/).
  - 산술 연산자에는 더하기(+), 빼기(-), 곱하기(*), 나누기(/)가 포함된다.

<br>

- The following `employees` table shows employee names and salaries:
  - 다음 `employees` 테이블은 employee 이름과 salary를 보여준다.

![img](/assets/img/sql-sololearn-filtering&function&subquery-04-03.png)

<br>

- The example below adds 500 to each employee's salary and selects the result:
  - 아래 예제는 각 employee의 salary에 500을 더하고, 그 결과를 select 한다.

```mysql
SELECT ID, FirstName, LastName, Salary+500 AS Salary
FROM employees;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-filtering&function&subquery-04-04.png)

<br>

> Parentheses can be used to force an operation to take priority over any other operators.
>
> 괄호를 사용해서 다른 연산보다 우선 수행할 수 있다.

> They are also used to improve code readability.
>
> 코드의 가독성을 높이기 위해서도 사용된다.

------

<br>

## QUIZ

- What do we call the function used for concatenation?
  - 연결에 사용되는 함수를 무엇이라고 하는가?

> `CONCAT`

<br>

- Type in the keyword used to create custom columns.
  - 사용자 정의 column을 생성하는 데 사용되는 키워드를 입력해라.

> `AS`

<br>

- Drag and drop from the options below to select concatenated "city" and "state" columns, represented with a new custom column named "new_address".
  - "city"와 "state" column을 select 하고, "new_address"라는 새로운 사용자 정의 column으로 나타내라.

```mysql
SELECT CONCAT (city, ',', state)
AS new_address
FROM customers;
```

<br>