---
layout: post
title: "06. 테이블 만들기 (JOIN, Table Operations)"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com) SQL 번역

<br>

# Creating a Table

###### 테이블 만들기

------

<br>

<br>

## SQL Tables

###### SQL 테이블

<br>

- A single database can house hundreds of tables, each playing its own unique role in the database schema.
  - 단일 데이터베이스는 수백 개의 테이블을 수용할 수 있으며, 각 테이블은 테이터베이스 스키마에서 고유한 역할을 수행한다.

<br>

- SQL tables are comprised of table rows and columns.
  - SQL 테이블은 테이블 row와 column으로 구성된다.
- Table columns are responsible for storing many different types of data, including numbers, texts, dates, and even files.
  - 테이블 column은 숫자, 텍스트, 날짜, 심지어 파일까지 다양한 타입의 데이터를 저장한다.

<br>

- The `CREATE TABLE` statement is used to create a new table.
  - `CREATE TABLE` 문은 새 테이블을 만드는 데 사용된다.
  - `CREATE TABLE`: is used to create a table in a database (데이터베이스에서 테이블을 만드는 데 사용된다)

<br>

> Creating a basic table involves naming the table and defining its columns and each column's data type.
>
> 기본 테이블을 생성하는 것은 테이블의 이름을 지정하고, column과 각 column의 데이터 타입을 정의한다.

<br>

<br>

- The basic syntax for the `CREATE TABLE` statement is as follows:
  - `CREATE TABLE` 문의 기본 문법은 다음과 같다.

```mysql
CREATE TABLE table_name (
	column_name1 data_type(size),
   column_name2 data_type(size),
   column_name3 data_type(size),
   ...
   columnN data_type(size)
);
```

<br>

- The `column_names` specify the names of the columns we want to create.
  - `column_names`는 생성하려는 column의 이름을 지정한다.
- The `data_type` parameter specifies what type of data the column can hold.
  - `data_type` 매개변수는 column이 보유할 수 있는 데이터 타입을 지정한다.
- For example, use `int` for whole numbers.
  - 예를 들어, 숫자에는 `int`를 사용한다.
- The `size` parameter specifies the maximum length of the table's column.
  - `size` 매개변수는 테이블 column의 최대 길이를 지정한다.

<br>

> Note the `parentheses` in the syntax.
>
> 구문의 `괄호`에 주의해라.

<br>

<br>

- Assume that you want to create a table called "Users" that consists of four columns: UserID, LastName, FirstName, and City.
  - 네 개의 UserID, LastName, FirstName, City column으로 구성된 "Users"라는 테이블을 만든다고 가정해보자.

```mysql
CREATE TABLE Users (
	UserID int,
   FirstName varchar(100),
   LastName varchar(100),
   City varchar(100)
);
```

<br>

> `varchar` is the data type that stores characters.
>
> `varchar`는 문자를 저장하는 데이터 타입이다.

> You specify the number of characters in the parentheses after the type.
>
> 타입 다음의 괄호 안에 있는 문자 수를 지정한다.

> So in the example above, our fields can hold max `100` characters long text.
>
> 위의 예제에서, field는 `100`자 길이의 텍스트를 저장할 수 있다.

------

<br>

## Data Types

###### 데이터 타입

<br>

- `Data types` specify the type of data for a particular column.
  - `데이터 타입`은 특정 column에 대한 데이터 타입을 지정한다.

<br>

- If a column called "LastName" is going to hold names, then that particular column should have a "varchar" (variable-length character) data type.
  - "LastName"이라는 column이 이름을 보유할 경우, 해당 특정 column에는 "varchar"(variable-length character) 데이터 타입이 있어야 한다.

<br>

- The most common data types:
  - 가장 일반적인 데이터 타입은 다음과 같다.

<br>

#### Numeric

- `INT`: A normal-sized integer that can be signed or unsigned.
  - 부호가 있거나 부호가 없는 정상 크기의 정수.
- `FLOAT`(M, D): A floating-point number that cannot be unsigned. You can optionally define the display length(M) and the number of decimals(D).
  - 부호를 사용할 수 없는 부동 소수점 숫자. 표시 길이(M)와 소수점 키(D)를 선택적으로 정의할 수 있다.
- `DOUBLE`(M, D): A double precision floating-point number that cannot be unsigned. You can optionally define the display length(M) and the number of decimals(D).
  - 부호를 사용할 수 없는 배정밀도 부동 소수점 숫자. 표시 길이(M)와 소수점 키(D)를 선택적으로 정의할 수 있다.

<br>

#### Data and Time

- `DATE`: A date in *YYYY-MM-DD* format.
  - *YYYY-MM-DD* 형식의 날짜.
- `DATETIME`: A data and time combination in YYYY-MM-DD HH:MM:SS format.
  - YYYY-MM-DD HH:MM:SS 형식의 날짜 및 시간 조합이다.
- `TIMESTAMP`: A timestamp, calculated from midnight, January 1, 1970.
  - 1970년 1월 1일 자정부터 계산된 타임스탬프.
- `TIME`: Stores the time in HH:MM:SS format.
  - 시간을 HH:MM:SS 형식으로 저장한다.

<br>

#### String Types

- `CHAR`(M): Fixed-length character string. Size is specified in parenthesis. Max 255 bytes.
  - 고정 길이 문자열. 크기는 괄호 안에 지정된다. 최대 255 바이트.
- `VARCHAR`(M): Variable-length character string. Max size is specified in parenthesis.
  - 변수 길이 문자열. 크기는 괄호 안에 지정된다.
- `BLOB`: "Binary Large Objects" and are used to store large amounts of binary data, such as images or other types of files.
  - 이미지나 다른 타입의 파일과 같은 많은 양의 이진 데이터를 저장하는 데 사용된다. "Binary Large Objects".
- `TEXT`: Large amount of text data.
  - 많은 양의 텍스트 데이터.

<br>

> Choosing the correct data type for your columns is the key to good database design.
>
> column에 올바른 데이터 타입을 선택하는 것이 좋은 데이터베이스 설계의 핵심이다.

------

<br>

## Primary Key

- The `UserID` is the best choice for our Users table's primary key.
  - `UserID`는 Users 테이블의 primary key에 가장 적합한 선택이다.
- Define it as a primary key during table creation, using the `PRIMARY KEY` keyword.
  - `PRIMARY KEY` 키워드를 사용해서 테이블을 생성하는 동안 primary key로 정의해라.

```mysql
CREATION TABLE Users (
	UserID int,
   FirstName varchar(100),
   LastName varchar(100),
   City varchar(100),
   PRIMARY KEY(UserID)
);
```

<br>

> Specify the column name in the parentheses of the PRIMARY KEY keyword.
>
> PRIMARY KEY 키워드의 괄호 안에 column 이름을 지정해라.

------

<br>

## Creating a Table

###### 테이블 만들기

<br>

- Now, when we run the query, our table will be created in the database.
  - 이제 query를 실행하면 데이터베이스에 테이블이 생성된다.

![sololearn img](/assets/img/sololearn-sql-join table operations-06-01.png)

<br>

> You can now use `INSERT INTO` queries to insert data into the table.
>
> 이제 `INSERT INTO` query를 사용해서 데이터를 테이블에 삽입할 수 있다.
>
> `INSERT INTO`: is used to insert new records in a table (테이블에 새로운 레코드를 삽입하는 데 사용된다)

------

<br>

## QUIZ

- Which choice is the correct command to use when creating a table?
  - 테이블을 만들 때 사용하는 올바른 명령은 무엇인가?

> `CREATE TABLE`

<br>

- Type in the keyword used as type for integer numbers.
  - 정수에 대한 타입으로 사용되는 키워드를 입력해라.

> `int`

<br>

- Type in the keyword used as type for a text in the lesson:
  - 텍스트 타입으로 사용되는 키워드를 입력해라.

> `varchar`

<br>

- Fill in the blanks to define a column named "some_column" of type varchar with a size of 50.
  - 크기가 50인 varchar 타입의 "some_column"이라는 column을 정의해라.

```mysql
some_column varchar(50)
```

<br>

- Drag and drop from the options below to make the "id" column a primary key.
  - "id" column을 primary key로 생성해라.

```mysql
PRIMARY KEY(id)
```

<br>

- Drag and drop from the options below to create a table with three columns: "id" as a primary key, username and password of type varchar.
  - 세 개의 column이 있는 테이블을 생성해라.
  - primary key로 "id"를, varchar 타입의 username과 password를 생성해라.

```mysql
CREATE TABLE test (
	id int,
   username varchar(30),
   password varchar(20),
   PRIMARY KEY(id)
);
```

<br>