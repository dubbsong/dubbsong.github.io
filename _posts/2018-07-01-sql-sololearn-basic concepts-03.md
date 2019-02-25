---
layout: post
title: "(Basic Concepts 03) SQL 구문 규칙"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

## Multiple Queries

###### 여러 query들

<br>

- SQL allows to run multiple queries or commands at the same time.
  - SQL은 여러 query 또는 명령을 동시에 실행할 수 있다.

<br>

- The following SQL statement selects the `FirstName` and `City` columns from the customers table:
  - 다음 SQL 문은 customers 테이블의 `FirstName`과 `City` column을 선택한다.

```mysql
SELECT FirstName FROM customers;
SELECT City FROM customers;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-basic concepts-03-01.png)

![img](/assets/img/sql-sololearn-basic concepts-03-02.png)

<br>

> Remember to end each SQL statement with a `semicolon` to indicate that the statement is complete and ready to be interpreted.
>
> 명령문이 완료되었거나 해석될 준비가 되었음을 나타내기 위해, 각 SQL 문을 `세미콜론`으로 끝내야 한다.

> We will use `semicolon` at the end of each SQL statement.
>
> 각 SQL 문 끝에 `세미콜론`을 사용한다.

------

<br>

## Case Sensitivity

###### 대소문자 구분

<br>

- SQL is case `insensitive`.
  - SQL은 `대소문자를 구분하지 않는다`.
- The following statements are equivalent and will produce the same result:
  - 다음 명령문들은 동일한 결과를 출력한다.

```mysql
select City from customers;
SELECT City FROM customers;
sElEct City From customers;
```

<br>

> It is common practice to write all SQL commands in `uuper-case`.
>
> 모든 SQL 명령어는 `대문자`로 작성하는 것이 일반적이다.

------

<br>

## Syntax Rules

###### 구문 규칙

<br>

- A single SQL statement can be placed on one or more text lines.
  - SQL 문은 하나 이상의 텍스트 line에 위치될 수 있다.
- In addition, multiple SQL statements can be combined on a single text line.
  - 게다가 여러 SQL 문을 하나의 텍스트 line에 결합시킬 수도 있다.

<br>

- White spaces and multiple lines are ignored in SQL.
  - 공백과 여러 line은 SQL에서 무시된다.
- For example, the following query is absolutely correct.
  - 예를 들어, 다음 query는 완전히 정확하다.

```mysql
SELECT	City

FROM customers;
```

<br>

- However, it is recommended to avoid unnecessary white spaces and lines.
  - 하지만, 불필요한 공백과 line은 피하는 것이 좋다.

<br>

> Combined with proper spacing and indenting, breaking up the commands into logical lines will make your SQL statements much easier to read and maintain.
>
> 적절한 간격과 들여쓰기를 결합해서 명령을 논리적으로 분리하면, SQL 문을 읽거나 유지하는 것이 더 쉬워진다.

------

<br>

## QUIZ

- Whenever you run multiple queries:
  - 여러 query를 실행할 때마다 ...

> `each query must end with a semicolon`
>
> 각 query는 세미콜론으로 끝나야 한다.

<br>

- SQL is:
  - SQL은 ...

> `Case insensitive`
>
> 대소문자를 구분하지 않는다.

<br>

- Which is true about whitespaces?
  - 공백에 대한 사실은 무엇인가?

> [ ] Line breaks divide a query into multiple queries
>
> [ ] Whitespaces affect query results
>
> [ ] `Whitespaces and line breaks are ignored`

<br>
