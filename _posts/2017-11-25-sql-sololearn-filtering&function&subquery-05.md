---
layout: post
title: "(Filtering, Function, Subquery 05) 함수"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

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
  - 다음 SQL query는 모든 *LastNames*를 대문자로 select 한다.

```mysql
SELECT FirstName, UPPER(LastName) AS LastName
FROM employees;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-filtering&function&subquery-05-01.png)

<br>

> If there are characters in the string that are not letters, this function will have no effect on them.
>
> 문자열에 문자가 아닌 문자가 있다면, 이 함수는 아무런 영향을 주지 않는다.

------

<br>

## SQRT & AVG function

###### SQRT & AVG 함수

<br>

- The `SQRT` function returns the square root of given value in the argument.
  - `SQRT` 함수는 인수에서 주어진 값의 제곱근을 반환한다.

<br>

- Let's calculate the square root of each Salary:
  - 각 Salary의 제곱근을 계산해보자.

```mysql
SELECT Salary, SQRT(Salary)
FROM employees;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-filtering&function&subquery-05-02.png)

<br>

- Similarly, the `AVG` function returns the average value of a numeric column:
  - 마찬가지로, `AVG` 함수는 숫자 column의 평균값을 반환한다.

```mysql
SELECT AVG(Salary) FROM employees;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-filtering&function&subquery-05-03.png)

<br>

> Another way to do the SQRT is to use POWER with the 1/2 exponent.
>
> SQRT를 수행하는 또 다른 방법은 1/2 지수로 POWER를 사용하는 것이다.

> However, SQRT seems to work faster than POWER in this case.
>
> 하지만 이 경우에 SQRT는 POWER 보다 빠르게 작동할 것이다.

------

<br>

## The SUM function

###### SUM 함수

<br>

- The `SUM` function is used to calculate the sum for a column's values.
  - `SUM` 함수는 column 값의 합계를 계산하는 데 사용된다.

<br>

- For example, to get the sum of all of the salaries in the employees table, our SQL query would look like this:
  - 예를 들어, employees 테이블의 모든 Salary 합계를 얻기 위한 SQL query는 다음과 같다.

```mysql
SELECT SUM(Salary) FROM employees;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-filtering&function&subquery-05-04.png)

<br>

> The sum of all of the employees' salaries is 31000.
>
> 모든 employee의 salary 합계는 31000이다.

------

<br>

## QUIZ

- What is the name of the function that converts the text to lowercase?
  - 텍스트를 소문자로 변환하는 함수의 이름은 무엇인가?

> `LOWER`

<br>

- Drag and drop from the options below to select the average cost from the "items" table.
  - "items" 테이블에서 평균 cost를 select 해라.

```mysql
SELECT AVG(cost) FROM items;
```

<br>

- Type in the aggregate function name used to calculate the sum of a column's values.
  - column 값의 합계를 계산하는 데 사용되는 총계 함수 이름은 무엇인가?

> `SUM`

<br>
