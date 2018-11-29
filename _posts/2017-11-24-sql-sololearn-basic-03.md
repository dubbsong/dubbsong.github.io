---
layout: post
title: "(Basic 03) SQL 구문 규칙"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

## Multiple Queries

###### 여러 query

<br>

- SQL allows to run multiple queries or commands at the same time.
  - SQL은 동시에 여러 query나 명령을 실행할 수 있다.

<br>

- The following SQL statement selects the `FirstName` and `City` columns from the customers table:
  - 다음 SQL 문은 customers 테이블에서 `FirstName`과 `City` column을 선택한다.

```mysql
SELECT FirstName FROM customers;
SELECT City FROM customers;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-basic-03-01.png)

<br>

![img](/assets/img/sql-sololearn-basic-03-02.png)

<br>

> Remember to end each SQL statement with a `semicolon` to indicate that the statement is complete and ready to be interpreted.
>
> 명령문이 완전하고 해석될 준비가 되었음을 나타내기 위해, 각 SQL 문을 `세미콜론`으로 끝내라.

------

<br>

## Case Sensitivity

###### 대소문자 구분

<br>

- SQL is case `insensitive`.
  - SQL은 `대소문자를 구분하지 않는다`.
- The following statements are equivalent and will produce the same result:
  - 다음 명령문은 동일하고, 동일한 결과를 출력한다.

```mysql
select City from customers;
SELECT City FROM customers;
sElEct City From customers;
```

<br>

> It is common practice to write all SQL commands in `upper-case`.
>
> 모든 SQL 명령을 `대문자`로 작성하는 것이 일반적이다.

------

<br>

## Syntax Rules

###### 구문 규칙

<br>

- A single SQL statement can be placed on one or more text lines.
  - 하나의 SQL 문은 하나 이상의 텍스트 줄에 위치시킬 수 있다.
- In addition, multiple SQL statements can be combined on a single text line.
  - 게다가, 여러 SQL 문을 하나의 텍스트 줄에 결합할 수 있다.

<br>

- Write spaces and multiple lines are ignored in SQL.
  - SQL에서는 공백과 여러 줄을 무시한다.
- For example, the following query is absolutely correct.
  - 예를 들어 다음 query는 완전히 정확하다.

```mysql
SELECT	City

FROM customers;
```

<br>

- However, it is recommended to avoid unnecessary white spaces and lines.
  - 하지만 불필요한 공백과 줄은 피하는 것이 좋다.

<br>

> Combined with proper spacing and indenting, breaking up the commands into logical lines will make your SQL statements much easier to read and maintain.
>
> 적절한 간격과 들여 쓰기를 결합해서 명령을 논리적으로 줄 바꿈하면, SQL 문을 읽거나 유지하는 것이 훨씬 쉬워진다.

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
  - SQL은 ...이다.

> [ ] Case sensitive
>
> [ ] `Case insensitive` (대소문자를 구분하지 않는다)

<br>

- Which is true about whitespaces?
  - 공백에 대해서 true인 것은 무엇인가?

> [ ] Whitespaces affect query results
>
> [ ] `Whitespaces and line breaks are ignored` (공백과 줄 바꿈은 무시된다)
>
> [ ] Line breaks divide a query into multiple queries

<br>
