---
layout: post
title: "SoloLearn SQL 번역 - 02. SQL Statements: SELECT (Basic Concepts)"
categories: dev
tags: db
---

## Basic SQL Commands

###### SQL 기본 명령어

<br>

- The SQL `SHOW` statement displays information contained in the database and its tables.
  - SQL `SHOW` 문은 데이터베이스와 테이블에 포함된 정보를 표시한다.
- This helpful tool lets you keep track of your database contents and remind yourself about the structure of your tables.
  - 이 유용한 도구를 사용하면 데이터베이스 내용을 추적하고, 테이블 구조에 대해 상기시킬 수 있다.
- For example, the `SHOW DATABASES` command lists the databases managed by the server.
  - 예를 들어, `SHOW DATABASES` 명령은 서버가 관리하는 데이터베이스를 나열한다.
  - `SHOW DATABASES`: Returns the list of all databases on the server (서버의 모든 데이터베이스 list를 반환한다)

```mysql
SHOW DATABASES
```

<br>

- Throughout the tutorial we will be using the MySQL engine and the PHPMyAdmin tool to run SQL queries.
  - 이 튜토리얼에서는 MySQL 엔진과 PHPMyAdmin 도구를 사용해서 SQL 쿼리를 실행한다.

<br>

> The easiest way to get MySQL and PHPMyAdmin is to install free tools like `XAMPP` or `WAMP`, which include all necessary installers.
>
> MySQL과 PHPMyAdmin을 얻는 가장 쉬운 방법은, 필요한 모든 설치 프로그램을 포함하는 `XAMPP`나 `WAMP`와 같은 무료 도구를 설치하는 것이다.

------

<br>

## Basic SQL Commands

###### SQL 기본 명령

<br>

- The `SHOW TABLES` command is used to display all of the tables in the currently selected MySQL database.
  - `SHOW TABLES` 명령은 현재 선택된 MySQL 데이터베이스의 모든 테이블을 표시하는 데 사용된다.

![sololearn img](/assets/img/sololearn-sql-basic concepts-02-01.png)

<br>

> For our example, we have created a database, `my_database`, with a table called `customers`.
>
> 이 예제에서는, `customers`라는 테이블이 있는 `my_database` 데이터베이스를 만들었다.

------

<br>

## Basic SQL Commands 02

- `SHOW COLUMNS` displays information about the columns in a given table.
  - `SHOW COLUMNS`는 주어진 테이블의 column에 대한 정보를 표시한다.

<br>

- The following example displays the columns in our `customers` table:
  - 다음 예제는 `customers` 테이블의 column을 표시한다.

```mysql
SHOW COLUMNS FROM customers
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-sql-basic concepts-02-02.png)

<br>

- SHOW COLUMNS displays the following values for each table column:
  - SHOW COLUMNS는 각 테이블 column에 대해 다음 값을 표시한다.

<br>

- `Field`: column name
- `Type`: column data type
- `Key`: indicates whether the column is indexed
- `Default`: default value assigned to the column
- `Extra`: may contain any additional information that is available about a given column

<br>

> The columns for the `customers` table have also been created using the PHPMyAdmin tool.
>
> `customers` 테이블의 columns은 PHPMyAdmin 도구를 사용해서 작성되었다.

------

<br>

## SELECT Statement

###### SELECT 문

<br>

- The `SELECT` statement is used to select data from a database.
  - `SELECT` 문은 데이터베이스에서 선택하는 데 사용된다.
  - `SELECT`: is used to select data from a database
- The result is stored in result table, which is called the `result-set`.
  - 결과는 `result-set`이라고 하는  result 테이블에 저장된다.

<br>

- A `query` may retrieve information from selected columns or from all columns in the table.
  - `query`는 선택한 column 또는 테이블의 모든 column에서 정보를 검색할 수 있다.
- To create a simple `SELECT` statement, specify the name(s) of the column(s) you need from the table.
  - 간단한 `SELECT` 문을 만들려면, 테이블에서 필요한 column의 이름을 지정해라.

<br>

- Syntax of the SQL `SELECT` Statement:
  - SQL `SELECT` 문의 구문:

```mysql
SELECT column_list
FROM table_name
```

<br>

- `column_list` includes one or more columns from which data is retrieved
  - `column_list`에는 데이터가 검색되는 하나 이상의 column이 포함된다.
- `table-name` is the name of the table from which the information is retrieved
  - `table-name`은 정보가 검색되는 테이블 이름이다.

<br>

- Below is the data from our `customers` table:
  - 아래는 `customers` 테이블의 데이터이다.

![sololearn img](/assets/img/sololearn-sql-basic concepts-02-03.png)

<br>

- The following SQL statement selects the `FirstName` from the `customers` table:
  - 다음 SQL 문은 `customers` 테이블에서 `FirstName`을 선택한다.

```mysql
SELECT FirstName FROM customers
```

<br>

![sololearn img](/assets/img/sololearn-sql-basic concepts-02-04.png)

------

<br>

## QUIZ

- Drag and drop from the options below to complete the command to list all of the databases.
  - drag and drop으로 모든 데이터베이스를 나열하는 명령을 완료해라.

```mysql
SHOW DATABASES
```

<br>

- Drag and drop from the options below to view a list of tables for the currently selected database.
  - 현재 선택한 데이터베이스에 대한 테이블 list를 봐라.

```mysql
SHOW TABLES
```

<br>

- Drag and drop from the options below to view the columns from the 'customers' table:
  - 'customers' 테이블의 column을 봐라.

```mysql
SHOW COLUMNS FROM customers
```

<br>

- Rearrange the code to select the "name" column values from the "customers" table.
  - 코드를 재정렬해서 "customers" 테이블에서 "name" column 값을 선택해라.

```mysql
SELECT name FROM customers
```

<br>
