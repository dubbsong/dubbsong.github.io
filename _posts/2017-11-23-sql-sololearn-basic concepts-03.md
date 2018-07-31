---
layout: post
title: "SoloLearn SQL 번역 - 03. SQL 문법 (Basic Concepts)"
categories: dev
tags: db
---

###### [SoloLearn SQL 번역](www.sololearn.com)

##### <br>

# SQL Syntax Rules

###### SQL 문법

<br>

## Multiple Queries

###### 여러 쿼리들

<br>

- SQL allows to run multiple queries or commands at the same time.
  - SQL은 동시에 여러 쿼리나 명령을 실행할 수 있게 한다.

<br>

- The following SQL statement selects the `FirstName` and `City` columns from the customers table:
  - 다음 SQL 문은 customers 테이블에서 `FirstName`과 `City` column을 선택한다.

```mysql
SELECT FirstName FROM customers;
SELECT City FROM customers;
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-sql-basic concepts-03-01.png)

![sololearn img](/assets/img/sololearn-sql-basic concepts-03-02.png)

<br>

> Remember to end each SQL statement with a `semicolon` to indicate that the statement is complete and ready to be interpreted.
>
> 명령문이 완전하고, 해석될 준비가 되었음을 나타내려면, 각 SQL 문을 `세미콜론`으로 끝내라.

> In this tutorial, we will use `semicolon` at the end of each SQL statement.
>
> 이 튜토리얼에서는, 각 SQL 문의 끝에 `세미콜론`을 사용한다.

------

<br>

## Case Sensitivity

###### 대소문자 구분

<br>

- SQL is case `insensitive`.
  - SQL은 대소문자를 구분하지 않는다.
- The following statements are equivalent and will produce the same result:
  - 다음 명령문은 동일하고, 동일한 결과를 생성한다.

```mysql
select City from customers;
SELECT City FROM customers;
sElEct City From customers;
```

<br>

> It is common practice to write all SQL commands in `upper-case`.
>
> 모든 SQL 명령은 `대문자`로 작성하는 것이 일반적이다.

------

<br>

## Syntax Rules

###### 문법

<br>

- A single SQL statement can be placed on one or more text lines.
  - 단일 SQL 문은 하나 이상의 텍스트 라인에 배치될 수 있다.
- In addition, multiple SQL statements can be combined on a single text line.
  - 게다가, 여러 SQL 문을 단일 텍스트 라인에 결합할 수 있다.

<br>

- White spaces and multiple lines are ignored in SQL.
  - SQL에서는 공백과 여러 라인을 무시한다.
- For example, the following query is absolutely correct.
  - 예를 들어, 다음 쿼리는 완전 정확하다.

```mysql
SELECT	City
FROM customer;
```

<br>

- However, it is recommended to avoid unnecessary white spaces and lines.
  - 하지만, 불필요한 공백과 라인은 피하는 것이 좋다.

<br>

> Combined with proper spacing and indenting, breaking up the commands into logical lines will make your SQL statements much easier to read and maintain.
>
> 적절한 간격 및 들여 쓰기와 결합해서 명령을 논리 라인으로 분리하면, SQL 문을 읽고 유지 보수하기가 훨씬 쉬워진다.

------

<br>

## QUIZ

- Whenever you run multiple queries:
  - 여러 쿼리들을 실행할 때마다:

> `Each query must end with a semicolon` (각 쿼리는 세미콜론으로 끝나야 한다)
>
> You get only the last query's result (마지막 쿼리의 결과만 가져온다)
>
> You get an error, because it's not possible to run more than one query (하나 이상의 쿼리를 실행할 수 없으므로, 에러가 발생한다)

<br>

- SQL is:
  - SQL은:

> Case sensitive
>
> `Case insensitive`

<br>

- Which is true about whitespaces?
  - 공백에 대해서 어떤 것이 사실인가?

> Line breaks divide a query into multiple queries (줄 바꿈은 쿼리를 여러 쿼리로 나눈다)
>
> Whitespaces affect query results (공백은 쿼리 결과에 영향을 미친다)
>
> Whitespaces and line breaks are ignored (공백과 줄 바꿈은 무시된다)

<br>
