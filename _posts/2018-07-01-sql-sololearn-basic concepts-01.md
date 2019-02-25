---
layout: post
title: "(Basic Concepts 01) 데이터베이스 소개"
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
  - 액세스의 용이성뿐만 아니라, 효율적인 관리와 업데이트가 가능하도록 구성되어 있다.

<br>

- A database is made up of `tables` that store relevant information.
  - 데이터베이스는 관련 정보를 저장하는 `테이블`로 구성되어 있다.

<br>

- For example, you would use a database, if you were to create a website like YouTube, which contains a lot of information like videos, usernames, passwords, comments.
  - 예를 들어, YouTube와 같은 웹사이트를 만드는 경우 데이터베이스를 사용해야 한다.
  - 동영상, 사용자 이름, 비밀번호, 댓글과 같은 많은 정보가 포함되기 때문이다.

------

<br>

## Database Tables

###### 데이터베이스 테이블

<br>

- A table stores and displays data in a structured format consisting of `columns` and `rows` that are similar to those seen in Excel spreadsheets.
  - 테이블은 구조화된 형식으로 데이터를 저장하고 표시한다.
  - Excel 스프레드시트에서 볼 수 있는 것과 유사한 `column`과 `row`로 이루어진다.

<br>

- Databases often contain multiple tables, each designed for a specific purpose.
  - 데이터베이스는 특정 목적을 위해 설계된 여러 테이블을 포함한다.
- For example, imagine creating a database table of `names` and `telephone numbers`.
  - 예를 들어, `name`과 `telephone numbers`의 데이터베이스 테이블을 생성해보자.

<br>

- First, we would set up columns with the titles *FirstName*, *LastName* and *TelephoneNumber*.
  - 먼저, *FirstName*, *LastName*, *TelephoneNumber*라는 제목으로 column을 설정해야 한다.
- Each table includes its own set of fields, based on the data it will store.
  - 각 테이블은 저장할 데이터에 따라 고유한 field를 포함한다.

![img](/assets/img/sql-sololearn-basic concepts-01-01.png)

<br>

> A table has a specified number of columns but can have any number of rows.
>
> 테이블은 지정한 수만큼 column을 가지지만, row는 얼마든지 가질 수 있다.

------

<br>

## Primary Keys

- A primary key is a field in the table that uniquely identifies the table records.
  - primary key는 테이블의 field이다.
  - 테이블 record를 특유의 방법으로 식별한다.

<br>

- The primary key's main features:
  - primary key의 주요 기능은 다음과 같다.

<br>

1. It must contain a `unique value` for each row.
   - 각 row에 대해 `고유한 값`을 포함해야 한다.
2. It cannot contain `NULL` values.
   - `NULL` 값을 포함할 수 없다.

<br>

- For example, our table contains a record for each name in a phone book.
  - 예를 들어, 우리 테이블은 전화번호부의 각 이름에 대한 record를 포함한다.
- The unique `ID` number would be a good choice for a primary key in the table, as there is always the chance for more than one person to have the same name.
  - 고유한 `ID` 숫자는 primary key에 대한 좋은 선택이다.
  - 둘 이상의 사용자가 동일한 이름을 가질 수 있기 때문이다.

![img](/assets/img/sql-sololearn-basic concepts-01-02.png)

<br>

> Tables are limited to `ONE` primary key each.
>
> 테이블은 각각 `1개`의 primary key로 제한된다.

> The primary key's value must be different for each row.
>
> primary key의 값은 각 row마다 달라야 한다.

------

<br>

## What is SQL?

###### SQL이란 무엇인가?

<br>

- Once you understand what a database is, understanding SQL is easy.
  - 데이터베이스가 무엇인지 이해한다면, SQL을 이해하는 것도 쉽다.
- `SQL` stands for `S`tructured `Q`uery `L`anguage.
  - `SQL`은 `S`tructured `Q`uery `L`anguage의 약자이다.
  - (구조화된 데이터 질의 언어)

<br>

- `SQL` is used to access and manipulate a `database`.
  - `SQL`은 `데이터베이스`에 액세스하고 조작하는 데 사용된다.
- `MySQL` is a `program` that understands `SQL`.
  - `MySQL`은 `SQL`을 이해하는 `프로그램`이다.

<br>

- SQL can:
  - SQL은 다음을 할 수 있다.

<br>

1. insert, update, or delete records in a database.
   - 데이터베이스에서 record를 삽입, 업데이트, 삭제할 수 있다.
2. create new databases, table, stored procedures, views.
   - 새 데이터베이스, 테이블, 저장 프로시저, 뷰를 생성한다.
3. retrieve data from a database, etc.
   - 데이터베이스로부터 데이터를 검색한다.

------

<br>

## QUIZ

- Which of the following is NOT true about a database?
  - 다음 중 데이터베이스에 대한 사실이 아닌 것은 무엇인가?

> [ ] A database is made up of "tables"
>
> [ ] A database is a collection of data
>
> [ ] `A database is a programming language`

<br>

- Tables are made up of:
  - 테이블은 ...로 구성된다.

> `columns and rows`

<br>

- The unique column used to identify the records is called:
  - record를 식별하는 데 사용되는 고유한 column을 ...라고 한다.

> `primary key`

<br>

- What is the name of the language used in creating & accessing databases?
  - 데이터베이스를 생성하고 액세스하는 데 사용되는 언어의 이름은 무엇인가?

> `SQL`

<br>