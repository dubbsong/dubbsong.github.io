---
layout: post
title: "03. UNION 연산자 (JOIN, Table Operations)"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com) SQL 번역

<br>

# UNION

###### UNION 연산자

------

<br>

<br>

## Set Operation

###### Set 연산자

<br>

- Occasionally, you might need to combine data from multiple tables into one comprehensive dataset.
  - 경우에 따라, 여러 테이블의 데이터를 하나의 포괄적인 dataset으로 결합해야 할 수도 있다.
- This may be for tables with similar data within the same database or maybe there is a need to combine similar data across databases or even across servers.
  - 이는 동일한 데이터베이스 내에서 유사한 데이터를 가진 테이블일 수도 있고, 데이터베이스 또는 심지어 여러 서버에서 유사한 데이터를 결합해야 할 필요가 있을 수도 있다.

<br>

- To accomplish this, use the `UNION` and `UNION ALL` operators.
  - 이를 수행하려면, `UNION`과 `UNION ALL` 연산자를 사용해라.
  - `UNION`: combines the result of two or more SELECT statements (두 개 이상 SELECT 문의 결과를 결합한다)

<br>

- `UNION` combines multiple datasets into a single dataset, and removes any existing duplicates.
  - `UNION`은 여러 dataset을 단일 dataset으로 결합하고, 기존 중복을 제거한다.
- `UNION ALL` combines multiple datasets into one dataset, but does not remove duplicate rows.
  - `UNION ALL`은 여러 dataset을 하나의 dataset으로 결합하지만, 중복 row를 제거하지는 않는다.

<br>

> UNION ALL is faster than UNION, as it does not perform the duplicate removal operation over the data set.
>
> UNION ALL은 data set에 대해 중복 제거 작업을 수행하지 않으므로, UNION보다 빠르다.

<br>

<br>

- The `UNION` operator is used to combine the result-sets of two or more `SELECT` statements.
  - `UNION` 연산자는 두 개 이상 `SELECT` 문의 result-set을 결합하는 데 사용된다.

<br>

- All `SELECT` statements within the `UNION` must have the `same number of columns`.
  - `UNION`의 모든 `SELECT` 문은 `동일한 수의 column`을 가져야 한다.
- The columns must also have the same `data types`.
  - column의 `data 타입`도 동일해야 한다.
- Also, the columns in each `SELECT` statement must be in the same order.
  - 각 `SELECT` 문의 column도 동일한 순서여야 한다.
- The syntax of `UNION` is as follows:
  - `UNION` 문법은 다음과 같다.

```mysql
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```

<br>

- Here is the `First` of two tables:
  - 다음은 두 개의 테이블 중 `첫 번째` 테이블이다.

![sololearn img](/assets/img/sololearn-sql-join table operations-03-01.png)

<br>

- And here is the `Second`:
  - 다음은 `두 번째` 테이블이다.

![sololearn img](/assets/img/sololearn-sql-join table operations-03-02.png)

<br>

```mysql
SELECT ID, FirstName, LastName, City FROM First
UNION
SELECT ID, FirstName, LastName, City FROM Second;
```

<br>

- The resulting table will look like this one:
  - 결과 테이블은 다음과 같다.

![sololearn img](/assets/img/sololearn-sql-join table operations-03-03.png)

<br>

> As you can see, the duplicates have been removed.
>
> 보다시피, 중복이 제거되었다.

<br>

#### TIP.

- If your columns don't match exactly across all queries, you can use a `NULL` (or any other) value such as:
  - column이 모든 query에서 정확히 일치하지 않으면, 다음과 같은 `NULL` (또는 다른 값) 값을 사용할 수 있다.

```mysql
SELECT FirstName, LastName, Company FROM businessContacts
UNION
SELECT FirstName, LastName, NULL FROM otherContacts;
```

------

<br>

## UNION ALL

###### UNION ALL 연산자

<br>

- `UNION ALL` selects all rows from each table and combines them into a single table.
  - `UNION ALL`은 각 테이블의 모든 row를 선택하고, 하나의 테이블로 결합한다.

<br>

- The following SQL statement uses `UNION ALL` to select data from the `First` and `Second` tables:
  - 다음 SQL 문은 `UNION ALL`을 사용해서 `First`와 `Second` 테이블의 데이터를 선택한다.

```mysql
SELECT ID, FirstName, LastName, City FROM First
UNION ALL
SELECT ID, FirstName, LastName, City FROM Second;
```

<br>

- The resulting table:
  - 결과 테이블:

![sololearn img](/assets/img/sololearn-sql-join table operations-03-04.png)

<br>

> As you can see, the result set includes the duplicate rows as well.
>
> 보다시피, 결과 set에는 중복 row가 포함된다.

------

<br>

## QUIZ

- Drag and drop from the options below to select name, cost, and bids from the "items" table.
  - "items" 테이블에서 이름, 비용, 입찰가를 선택해라.
- Select only those items whose bids are greater than 123.
  - 입찰가가 123보다 큰 항목만 선택해라.

```mysql
SELECT name, cost, bids
FROM items
WHERE bids > 123;
```

<br>

- To perform a union operation:
  - union 작업을 수행하려면:

> `Columns in queries must be the same`
>
> `query의 column은 동일해야 한다`

<br>

- Type in the command to unite the query results without removing the duplicates.
  - 명령을 입력해서 중복 결과를 제거하지 않고, query 결과를 통합해라.

> `UNION ALL`

<br>
