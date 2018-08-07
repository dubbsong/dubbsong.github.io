---
layout: post
title: "05. 함수 (Filtering, Functions, Subqueries)"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com) SQL 번역

<br>

# Functions

###### 함수

------

<br>

<br>

## The UPPER Function

###### UPPER 함수

<br>

- The `UPPER` function converts all letters in the specified string to uppercase.
  - `UPPER` 함수는 지정된 문자열의 모든 문자를 대문자로 변환한다.
- The `LOWER` function converts the string to lowercase.
  - `LOWER` 함수는 문자열을 소문자로 변환한다.

<br>

- The following SQL query selects all *LastNames* as uppercase:
  - 다음 SQL query는 모든 *LastNames*를 대문자로 선택한다.

```mysql
SELECT FirstName, UPPER(LastName) AS LastName
FROM employees;
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-sql-filtering functions subqueries-05-01.png)

<br>

> If there are characters in the string that are not letters, this function will have no effect on them.
>
> 문자열에 문자가 아닌 문자가 있으면, 함수는 아무런 영향을 미치지 않는다.

------

<br>

## SQRT and AVG

- The `SQRT` function returns the square root of given value in the argument.
  - `SQRT` 함수는 인수에서 주어진 값의 제곱근을 반환한다.
  - `SQRT`: Returns the square root (제곱근을 반환한다)

<br>

- Let's calculate the square root of each Salary:
  - 각 Salary의 제곱근을 계산해보자.

```mysql
SELECT Salary, SQRT(Salary)
FROM employees;
```

<br>

- Result:

![sololearn img](/aseets/img/sololearn-sql-filtering functions subqueries-05-02.png)

<br>

- Similarly, the `AVG` function returns the average value of a numeric column:
  - 마찬가지로, `AVG` 함수는 숫자 column의 평균값을 반환한다.
  - `AVG`: Returns the average value (평균값을 반환한다)

```mysql
SELECT AVG(Salary) FROM employees;
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-sql-filtering functions subqueries-05-03.png)

------

<br>

## The SUM function

###### SUM 함수

<br>

- The `SUM` function is used to calculate the sum for a column's values.
  - `SUM` 함수는 column 값의 합계를 계산하는 데 사용된다.
  - `SUM`: Returns the sum (합계를 반환한다)

<br>

- For example, to get the sum of all of the salaries in the employees table, our SQL query would look like this:
  - 예를 들어, employees 테이블의 모든 급여 합계를 얻으려면, SQL query는 다음과 같다.

```mysql
SELECT SUM(Salary) FROM employees;
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-sql-filtering functions subqueries-05-04.png)

<br>

> The sum of all of the employees' salaries is 31000.
>
> 모든 직원의 급여 합계는 31000이다.

------

<br>

## QUIZ

- What is the name of the function that converts the text to lowercase?
  - 텍스트를 소문자로 변환하는 함수의 이름은 무엇인가?

> `LOWER`

<br>

- Drag and drop from the options below to select the average cost from the "items" table.
  - "items" 테이블에서 평균 비용을 선택해라.

```mysql
SELECT AVG(cost)
FROM items;
```

<br>

- Type in the aggregate function name used to calculate the sum of a column's values.
  - column 값의 합계를 계산하는 데 사용되는 총계 함수 이름을 입력해라.

> `SUM`

<br>
