---
layout: post
title: "(Basic 01) 데이터베이스 소개"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

## A Database

###### 데이터베이스

<br>

- A `database` is a collection of data that is organized in a manner that facilitates ease of access, as well as efficient management and updating.
  - `데이터베이스`는 데이터 모음이다.
  - 효율적인 관리와 업데이트뿐만 아니라, 접근이 용이하게 구성되어 있다.

<br>

- A database is made up of `tables` that store relevant information.
  - 데이터베이스는 관련 정보를 저장하는 `테이블`로 구성된다.

<br>

- For example, you would use a database, if you were to create a website like YouTube, which contains a lot of information like videos, usernames, passwords, comments.
  - 예를 들어 YouTube와 같은 웹사이트를 만들려면 데이터베이스를 사용해야 한다.
  - 여기에는 동영상, 사용자 이름, 비밀번호, 댓글과 같은 많은 정보가 포함된다.

![img](/assets/img/sql-sololearn-basic-01-01.png)

------

<br>

## Database Tables

###### 데이터베이스 테이블

<br>

- A table stores and displays data in a structured format consisting of `columns` and `rows` that are similar to those seen in Excel spreadsheets.
  - 테이블은 데이터를 구조화된 형식으로 저장하고 표시한다.
  - Excel 스프레드시트에서 볼 수 있는 것과 유사한 `column`과 `row`로 구성된다.

<br>

- Databases often contain multiple tables, each designed for a specific purpose.
  - 데이터베이스는 종종 특정 목적을 위해 설계된 여러 테이블을 포함한다.
- For example, imagine creating a database table of `names` and `telephone numbers`.
  - 예를 들어, `names`과 `telephone numbers`의 데이터베이스 테이블 생성을 생각해보자.

<br>

- First, we would set up columns with the titles *FirstName*, *LastName* and *TelephoneNumber*.
  - 먼저, *FirstName*, *LastName*, *TelephoneNumber*라는 제목으로 column을 설정해야 한다.

<br>

- Each table includes its own set of fields, based on the data it will store.
  - 각 테이블에는 저장할 데이터를 기반으로 자체 field set이 포함된다.

![img](/assets/img/sql-sololearn-basic-01-02.png)

<br>

> A table has a specified number of columns but can have any number of rows.
>
> 테이블에는 지정된 수의 column이 있지만, 여러 row를 가질 수 있다.

------

<br>

## Primary Keys

- A primary key is a field in the table that uniquely identifies the table records.
  - primary key는 테이블 record를 고유하게 식별하는 테이블의 field이다.

<br>

#### The primary key's main features:

###### primary key의 주요 기능:

<br>

- It must contain a `unique value` for each row:
  - 각 row에 대해 `고유한 값`을 포함해야 한다.
- It cannot contain `NULL` values.
  - `NULL` 값을 포함할 수 없다.

<br>

- For example, our table contains a record for each name in a phone book.
  - 예를 들어 우리 테이블은 전화번호부에서 각 name에 대한 record를 포함한다.
- The unique `ID` number would be a good choice for a primary key in the table, as there is always the chance for more than one person to have the same name.
  - 테이블에서 primary key에 고유한 `ID` 숫자를 사용하는 것은 좋은 선택이다.
  - 둘 이상의 사람이 동일한 name을 가질 수 있기 때문이다.

![img](/assets/img/sql-sololearn-basic-01-03.png)

<br>

> Tables are limited to `ONE` primary key each.
>
> 테이블은 primary key를 각 `1개`로 제한한다.

> The primary key's value must be different for each row.
>
> primary key의 값은 각 row마다 달라야 한다.

------

<br>

## What is SQL?

###### SQL이란 무엇인가?

<br>

- Once you understand what a database is, understanding SQL is easy.
  - 일단 데이터베이스가 무엇인지 이해하면, SQL을 이해하는 것이 쉽다.

- `SQL` stands for `S`tructured `Q`uery `L`anguage.
  - `SQL`은 `S`tructured `Q`uery `L`anguage(구조화 쿼리 언어)의 약자이다.

<br>

- `SQL` is used to access and manipulate a `database`.
  - `SQL`은 `데이터베이스` 접근과 조작에 사용된다.
- `MySQL` is a `program` that understands `SQL`.
  - `MySQL`은 `SQL`을 이해하는 `프로그램`이다.

<br>

#### SQL can:

###### SQL은 다음을 할 수 있다.

<br>

- insert, update, or delete records in a database.
  - 데이터베이스의 record를 삽입, 업데이트, 제거할 수 있다.
- create new databases, table, stored procedures, views.
  - 새 데이터베이스, 테이블, stored procedure, view를 생성한다.
  - `stored procedure`: 데이터베이스 시스템의 고속화 기법. 자주 사용하는 일련의 명령 집합(처리 절차)을 사전에 컴파일(번역)하여 바로 실행 가능한 상태의 모듈로 데이터베이스 관리 시스템(DBMS)에 수용하는 것을 말한다.
- retrieve data from a database, etc.
  - 데이터베이스로부터 데이터를 검색한다.

------

<br>

## QUIZ

- Which of the following is NOT true about a database?
  - 다음 중 데이터베이스에 대해 true가 아닌 것은 무엇인가?

> [ ] A database is made up of "tables"
>
> [ ] A database is a collection of data
>
> [ ] `A database is a programming language`

<br>

- Tables are made up of:
  - 테이블은 ...로 구성된다.

> `Columns and rows`

<br>

- The unique column used to identify the records is called:
  - record를 식별하는 데 사용되는 고유한 column을 ...라고 한다.

> `primary key`

<br>

- What is the name of the language used in creating & accessing databases?
  - 데이터베이스를 생성하고 액세스하는 데 사용되는 언어의 이름은 무엇인가?

> `SQL`

<br>