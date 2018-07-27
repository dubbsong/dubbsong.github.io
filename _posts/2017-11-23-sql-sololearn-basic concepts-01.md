---
layout: post
title: "SoloLearn SQL 번역 - 01. Introduction to Databases (Basic Concepts)"
categories: dev
tags: db
---

## A Database

###### 데이터베이스

<br>

- A `database` is a collection of data that is organized in a manner that facilitates ease of access, as well as efficient management and updating.
  - `데이터베이스`는 일정한 방식으로 구성되는 데이터 모음이다.
  - 효율적인 관리와 업데이트는 물론, 접근을 쉽게 할 수 있도록 구성된다.

<br>

- A database is made up of `tables` that store relevant information.
  - 데이터베이스는 관련 정보를 저장하는 `테이블`로 구성된다.

<br>

- For example, you would use a database, if you were to create a website like YouTube, which contains a lot of information like videos, usernames, passwords, comments.
  - 예를 들어, YouTube와 같은 웹사이트를 만들려면, 데이터베이스를 사용해야 한다.
  - 여기에는 동영상, 사용자 이름, 패스워드, 댓글과 같은 많은 정보가 포함되어 있다.

![sololearn img](/assets/img/sololearn-sql-basic concepts-01-01.png)

------

<br>

## Database Tables

###### 데이터베이스 테이블

<br>

- A table stores and displays data in a structured format consisting of `columns` and `rows` that are similar to those seen in Excel spreadsheets.
  - 테이블은 구조화된 형식으로 데이터를 저장하고 표시한다.
  - 엑셀 스프레드 시트에서 볼 수 있는 것과 유사한 `column(열)`과 `row(행)`으로 구성되어 있는.

<br>

- Database often contain multiple tables, each designed for a specific purpose.
  - 데이터베이스는 종종 특정 목적을 위해 설계된 여러 테이블을 포함한다.
- For example, imagine creating a database table of `names` and `telephone numbers`.
  - 예를 들어, `이름`과 `전화번호`의 데이터베이스 테이블을 만드는 것을 상상해보자.

<br>

- First, we would set up columns with the titles *FirstName*, *LastName* and *TelephoneNumber*.
  - 먼저, *FirstName*, *LastName*, *TelephoneNumber*라는 제목으로 column을 설정할 것이다.

<br>

- Each table includes its own set of fields, based on the data it will store.
  - 각 테이블에는 저장할 데이터를 기반으로, 자체 field 집합이 포함된다.

![sololearn img](/assets/img/sololearn-sql-basic concepts-01-02.png)

------

<br>

## Primary Keys

###### 기본 키

<br>

- A primary key is a field in the table that uniquely identifies the table records.
  - 기본 키는 테이블 레코드를 고유하게 식별하는 테이블의 field이다.

<br>

#### The primary key's main features:

###### 기본 키의 주요 기능

<br>

- It must contain a `unique value` for each row.
  - 각 row에 대해 `고유한 값`을 포함해야 한다.
- It cannot contain `NULL` values.
  - `NULL` 값을 포함할 수 없다.
  - `NULL`: An absence of value (값의 부재)

<br>

- For example, our table contains a record for each name in a phone book.
  - 예를 들어, 테이블에는 전화번호부의 각 이름에 대한 레코드가 포함되어 있다.
- The unique `ID` number would be a good choice for a primary key in the table, as there is always the chance for more than one person to have the same name.
  - 고유한 `ID` 번호는 테이블에 있는 기본 키에 대해 좋은 선택이다.
  - 둘 이상의 사용자가 동일한 이름을 가지는 상황이 항상 있기 때문이다.

![sololearn img](/assets/img/sololearn-sql-basic concepts-01-03.png)

<br>

> Tables are limited to `ONE` primary key each.
>
> 테이블은 각각 `1개`의 기본 키로 제한된다.

> The primary key's value must be different for each row.
>
> 기본 키의 값은 각 row마다 달라야 한다.

------

<br>

## What is SQL?

###### SQL은 무엇인가?

<br>

- Once you understand what a database is, understanding SQL is easy.
  - 일단 데이터베이스가 무엇인지 이해하면, SQL을 쉽게 이해할 수 있다.
- `SQL` stands for `S`tructured `Q`uery `L`anguage.
  - `SQL`은 `S`tructured `Q`uery `L`anguage의 약자이다.

<br>

- `SQL` is used to access and manipulate a `database`.
  - `SQL`은 `데이터베이스`에 액세스하고 조작하는 데 사용된다.
- `MySQL` is a `program` that understands `SQL`.
  - `MySQL`은 `SQL`을 이해하는 프로그램이다.

<br>

#### SQL can:

- insert, update, or delete records in a database.
  - 데이터베이스에서 레코드를 삽입, 업데이트, 삭제할 수 있다.
- create new databases, table, stored procedures, views.
  - 새 데이터베이스, 테이블, 저장되는 절차, view를 만들 수 있다.
- retrieve data from a database, etc.
  - 데이터베이스에서 데이터를 검색할 수 있다.

<br>

> SQL is an ANSI (American National Standards Institute) standard, but there are different versions of the SQL language.
>
> SQL은 ANSI 표준이지만, 다른 SQL 언어 버전이 있다.

> Most SQL database programs have their own proprietary extensions in addition to the SQL standard, but all of them support the major commands.
>
> 대부분의 SQL 데이터베이스 프로그램은 SQL 표준 외에도 자체 독자적인 확장 프로그램을 가지고 있지만, 모두 주요 명령을 지원한다.

------

<br>

## QUIZ

- Which of the following is NOT true about a database?
  - 다음 중 데이터베이스에 대해 사실이 아닌 것은 어떤 것인가?

> [ ] A database is a collection of data
>
> [ ] A database is made up of "tables"
>
> [ ] `A database is a programming language`

<br>

- Tables are made up of:
  - 테이블은 다음으로 구성된다.

> [ ] Columns only
>
> [ ] Rows, but no columns
>
> [ ] `Columns and rows`

<br>

- The unique column used to identify the records is called:
  - 레코드를 식별하는 데 사용되는 고유한 column을 뭐라고 부르는가?

> `primary key`

<br>

- What is the name of the language used in creating & accessing databases?
  - 데이터베이스를 만들고 액세스하는 데 사용되는 언어의 이름은 무엇인가?

> `sql`

<br>