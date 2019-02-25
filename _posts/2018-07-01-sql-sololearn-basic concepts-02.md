---
layout: post
title: "(Basic Concepts 02) SELECT 문"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

## Basic SQL Commands

###### 기본 SQL 명령어

<br>

- The SQL `SHOW` statement displays information contained in the database and its tables.
  - SQL `SHOW` 문은 데이터베이스와 테이블에 포함된 정보를 표시한다.
- This helpful tool lets you keep track of your database contents and remind yourself about the structure of your tables.
  - 데이터베이스 내용을 파악하고, 테이블 구조에 대해 미리 알 수 있다.
- For example, the `SHOW DATABASES` command lists the databases managed by the server.
  - `SHOW DATABASES` 명령어는 서버가 관리하는 데이터베이스를 나열한다.

```mysql
SHOW DATABASES
```

<br>

- Throughout the tutorial we will be using MySQL engine and the PHPMyAdmin tool to run SQL queries.
  - 이 튜토리얼에서는 MySQL 엔진과 PHPMyAdmin 도구를 사용해서 SQL query를 실행한다.

<br>

<br>

- The `SHOW TABLES` commands is used to display all of the tables in the currently selected MySQL database.
  - `SHOW TABLES` 명령어는 현재 선택한 MySQL 데이터베이스의 모든 테이블을 표시하는 데 사용된다.

<br>

<br>

- `SHOW COLUMNS` displays information about the columns in a given table.
  - `SHOW COLUMNS`는 테이블의 column에 대한 정보를 표시한다.

<br>

- The following example displays the columns in our `customers` table:
  - 다음 예제는 `customers` 테이블의 column을 표시한다.

```mysql
SHOW COLUMNS FROM customers
```

<br>

- SHOW COLUMNS displays the following values for each table column:
  - SHOW COLUMNS는 각 테이블 column에 대한 다음 값을 표시한다.

<br>

- `Field`: column name
  - column 이름
- `Type`: column data type
  - column 데이터 type
- `Key`: indicates whether the column is indexed
  - column이 인덱싱 되는지를 나타낸다.
- `Default`: default value assigned to the column
  - column에 지정된 기본 값
- `Extra`: may contain any additional information that is available about a given column
  - column에 대해 사용할 수 있는 추가 정보가 포함될 수 있다.

------

<br>

## SELECT Statement

###### SELECT 문

<br>

- The `SELECT` statement is used to select data from a database.
  - `SELECT` 문은 데이터베이스의 데이터를 선택하는 데 사용된다.
- The result is stored in a result table, which is called the `result-set`.
  - 결과는 `result-set`이라고 하는 결과 테이블에 저장된다.

<br>

- A `query` may retrieve information from selected columns or from all columns in the table.
  - `query`는 선택한 column 또는 테이블의 모든 column에서 정보를 검색할 수 있다.
- To create a simple SELECT statement, specify the name(s) of the column(s) you need from the table.
  - 간단한 SELECT 문을 생성하려면, 테이블에서 필요한 column의 이름을 지정한다.

<br>

- Syntax of the SQL `SELECT` Statement:
  - SQL `SELECT` 문의 구문은 다음과 같다.

```mysql
SELECT column_list FROM table_name
```

<br>

- `column_list` includes one or more columns from which data is retrieved.
  - `column_list`에는 데이터가 검색되는 하나 이상의 column이 포함된다.
- `table_name` is the name of the table from which the information is retrieved.
  - `table_name`은 정보가 검색되는 테이블의 이름이다.

<br>

- Below is the data from our `customers` table:
  - 아래 이미지는 `customers` 테이블의 데이터이다.

![img](/assets/img/sql-sololearn-basic concepts-02-01.png)

<br>

- The following SQL statement selects the `FirstName` from the `customers` table:
  - 다음 SQL 문은 `customers` 테이블의 `FirstName`을 선택한다.

```mysql
SELECT FirstName FROM customers
```

![img](/assets/img/sql-sololearn-basic concepts-02-02.png)

<br>

> A SELECT statement retrieves zero or more rows from one or more database tables.
>
> SELECT 문은 하나 이상의 데이터베이스 테이블에서 0개 이상의 row를 검색한다.

------

<br>

## QUIZ

- Drag and drop from the options below to complete the command to list all of the databases.
  - 모든 데이터베이스를 나열하는 명령어를 작성해라.

```mysql
SHOW DATABASES
```

<br>

- Drag and drop from the options below to view a list of tables for the currently selected database.
  - 현재 선택한 데이터베이스의 테이블을 나열해라.

```mysql
SHOW TABLES
```

<br>

- Drag and drop from the options below to view the columns from the 'customers' table:
  - 'customers' 테이블의 column을 표시해라.

```mysql
SHOW COLUMNS FROM customers
```

<br>

- Rearrange the code to select the "name" column values from the "customers" table.
  - "customers" 테이블의 "name" column을 선택해라.

```mysql
SELECT name FROM customers
```

<br>