---
layout: post
title: "(Basic 02) SQL 문: SELECT"
categories: etc
tags: sql
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

## Basic SQL Commands

###### 기본 SQL 명령

<br>

- The SQL `SHOW` statement displays information contained in the database and its tables.
  - SQL `SHOW` 문은 데이터베이스와 테이블에 포함된 정보를 표시한다.
- This helpful tool lets you keep track of your database contents and remind yourself about the structure of your tables.
  - 이를 사용하면 데이터베이스 content를 계속 파악할 수 있고, 테이블 구조에 대해 상기시킬 수 있다.
- For example, the `SHOW DATABASES` command lists the databases managed by the server.
  - 예를 들어 `SHOW DATABASES` 명령은 서버가 관리하는 데이터베이스를 나열한다.

```mysql
SHOW DATABASES
```

<br>

- Throughout the tutorial we will be using the MySQL engine and the PHPMyAdmin tool to run SQL queries.
  - 이 튜토리얼에서는 MySQL 엔진과 PHPMyAdmin 도구를 사용해서 SQL query를 실행한다.

<br>

> The easiest way to get MySQL and PHPMyAdmin is to install free tools like `XAMPP` or `WAMP`, which include all necessary installers.
>
> MySQL과 PHPMyAdmin을 사용하는 가장 쉬운 방법은, 필요한 모든 설치 프로그램을 포함하고 있는  `XAMPP`나 `WAMP`와 같은 무료 도구를 설치하는 것이다.

<br>

<br>

- The `SHOW TABLES` command is used to display all of the tables in the currently selected MySQL database.
  - `SHOW TABLES` 명령은 현재 선택된 MySQL 데이터베이스의 모든 테이블을 표시하는 데 사용된다.

![img](/assets/img/sql-sololearn-basic-02-01.png)

<br>

> For our example, we have created a database, `my_database`, with a table called `customers`.
>
> 위 예제에서 `customers`라는 테이블이 있는 `my_database` 데이터베이스를 생성했다.

<br>

<br>

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

![img](/assets/img/sql-sololearn-basic-02-02.png)

<br>

- SHOW COLUMNS displays the following values for each table column:
  - SHOW COLUMNS는 각 테이블 column에 대해 다음 값을 표시한다.

<br>

- `Field`: column name
  - column 이름
- `Type`: column data type
  - column 데이터 type
- `Key`: indicates whether the column is indexed
  - column이 index 되는지 여부를 나타낸다.

- `Default`: default value assigned to the column
  - column에 할당된 기본값
- `Extra`: may contain any additional information that is available about a given column
  - 주어진 column에 대해 사용할 수 있는 추가 정보가 포함될 수 있다.

<br>

> The columns for the `customers` table have also been created using the PHPMyAdmin tool.
>
> `customers` 테이블의 column은 PHPMyAdmin을 사용해서 생성되었다.

------

<br>

## SELECT Statement

###### SELECT 문

<br>

- The `SELECT` statement is used to select data from a database.
  - `SELECT` 문은 데이터베이스에서 데이터를 선택하는 데 사용된다.
- The result is stored in a result table, which is called the `result-set`.
  - 결과는 `result-set`이라고 하는 결과 테이블에 저장된다.

<br>

- A `query` may retrieve information from selected columns or from all columns in the table.
  - `query`는 선택한 column 또는 테이블의 모든 column에서 정보를 검색할 수 있다.
- To create a simple SELECT statement, specify the name(s) of the column(s) you need from the table.
  - 간단한 SELECT 문을 생성하기 위해, 테이블에서 필요한 column의 이름을 지정한다.

<br>

- Syntax of the SQL SELECT Statement:
  - SQL SELECT 문의 구문:

```mysql
SELECT column_list FROM table_name
```

<br>

- `column_list` includes one or more columns from which data is retrieved.
  - `column_list`에는 데이터가 검색되는 하나 이상의 column을 포함한다.
- `table_name` is the name of the table from which the information is retrieved.
  - `table_name`은 정보가 검색되는 테이블의 이름이다.

<br>

- Below is the data from our `customers` table:
  - 아래는 `customers` 테이블의 데이터이다.

![img](/assets/img/sql-sololearn-basic-02-03.png)

<br>

- The following SQL statement selects the `FirstName` from the `customers` table:
  - 다음 SQL 문은 `customers` 테이블에서 `FirstName`을 선택한다.

```mysql
SELECT FirstName FROM customers
```

<br>

![img](/assets/img/sql-sololearn-basic-02-04.png)

<br>

> A SELECT statement retrieves zero or more rows from one or more database tables.
>
> SELECT 문은 하나 이상의 데이터베이스 테이블에서 0개 이상의 row를 검색한다.

------

<br>

## QUIZ

- Drag and drop from the options below to complete the command to list all of the databases.
  - 모든 데이터베이스를 나열하는 명령을 완성해라.

```mysql
SHOW DATABASES
```

<br>

- Drag and drop from the options below to view a list of tables for the currently selected database.
  - 현재 선택된 데이터베이스에 대한 테이블 list를 표시해라.

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
  - "customers" 테이블에서 "name" column 값을 선택해라.

```mysql
SELECT name FROM customers
```

<br>