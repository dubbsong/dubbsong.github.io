---
layout: post
title: "04. 여러 column 선택하기 (Basic Concepts)"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

# Selecting Multiple Columns

###### 여러 column 선택하기

<br>

- As previously mentioned, the SQL `SELECT` statement retrieves records from tables in your SQL database.
  - 앞서 언급한 것처럼, SQL `SELECT` 문은 SQL 데이터베이스의 테이블에서 레코드를 검색한다.
  - `SELECT`: is used to select data from a database (데이터베이스에서 데이터를 선택하는 데 사용된다)

<br>

- You can select multiple table columns at once.
  - 한 번에 여러 테이블 column을 선택할 수 있다.
- Just list the column names, separated by `commas`:
  - `쉼표`로 구분된 column 이름을 나열해보자.

```mysql
SELECT FirstName, LastName, City
FROM customers;
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-sql-basic concepts-04-01.png)

<br>

> Do not put a comma after the `last` column name.
>
> `마지막` column 이름 뒤에 쉼표를 넣지 마라.

------

<br>

## Selecting All Columns

###### 모든 column 선택하기

<br>

- To retrieve all of the information contained in your table, place an `asterisk (*)` sign after the `SELECT` command, rather than typing in each column names separately.
  - 테이블에 포함된 모든 정보를 검색하려면, 각 column 이름을 별도로 입력하는 대신, `SELECT` 명령 뒤에 `별표 (*)` 기호를 사용해라.

<br>

- The following SQL statement selects all of the columns in the `customers` table:
  - 다음 SQL 문은 `customers` 테이블의 모든 column을 선택한다.

```mysql
SELECT * FROM customers;
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-sql-basic concepts-04-02.png)

<br>

> In SQL, the asterisk means `all`.
>
> SQL에서 별표는 `모두`를 의미한다.

------

<br>

## QUIZ

- Fill in the blanks to select name and city from the "people" table.
  - "people" 테이블에서 name과 city를 선택해라.

```mysql
SELECT name, city FROM people;
```

<br>

- Type in the missing symbol to select all of the columns from the "students" table.
  - 누락된 기호를 입력해서 "students" 테이블의 모든 column을 선택해라.

```mysql
SELECT * FROM students;
```

<br>
