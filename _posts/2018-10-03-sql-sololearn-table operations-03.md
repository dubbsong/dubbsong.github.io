---
layout: post
title: "(JOIN, Table Operations 03) UNION 연산자"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

### Set Operation

###### 연산 설정하기

<br>

- Occasionally, you might need to combine data from multiple tables into one comprehensive dataset.
  - 때로는 여러 테이블의 데이터를 하나의 종합적인 dataset으로 결합해야 할 수도 있다.
- This may be for tables with similar data within the same database or maybe there is a need to combine similar data across databases or even across servers.
  - 이는 동일한 데이터베이스 내에서 유사한 데이터를 가진 테이블일 수도 있다.
  - 데이터베이스 또는 여러 서버에서 유사한 데이터를 결합해야 할 수도 있다.

<br>

- To accomplish this, use the `UNION` and `UNION ALL` operators.
  - 이를 수행하기 위해, `UNION`과 `UNION ALL` 연산자를 사용한다.

<br>

- `UNION` combines multiple datasets into a single dataset, and removes any existing duplicates.
  - `UNION`은 여러 dataset들을 하나의 dataset으로 결합하고, 기존 중복들을 제거한다.
- `UNION ALL` combines multiple datasets into one dataset, but does not remove duplicate rows.
  - `UNION ALL`은 여러 dataset들을 하나의 dataset으로 결합하지만, 중복 row들을 제거하지는 않는다.

<br>

> UNION ALL is faster than UNION, as it does not perform the duplicate removal operation over the dataset.
>
> UNION ALL은 dataset에 대해 중복 제거 연산을 하지 않으므로, UNION보다 빠르다.

------

<br>

### UNION

###### UNION 연산자

<br>

- The `UNION` operator is used to combine the result-sets of two or more SELECT statements.
  - `UNION` 연산자는 두 개 이상 SELECT 문의 result-set을 결합하는 데 사용된다.

<br>

- All SELECT statements within the UNION must have the `same number of columns`.
  - UNION의 모든 SELECT 문은 `동일한 수의 column`을 가져야 한다.
- The columns must also have the same `data types`.
  - column의 `데이터 타입`도 동일해야 한다.
- Also, the columns in each SELECT statement must be in the same order.
  - 각 SELECT 문의 column도 동일한 순서여야 한다.

<br>

- The syntax of UNION is as follows:
  - UNION의 구문은 다음과 같다.

```sql
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```

<br>

- Here is the `First` of two tables:
  - 다음은 두 테이블 중 `첫 번째` 테이블이다.

![img](/assets/img/sql-sololearn-table operations-03-01.png)

<br>

- And here is the `Second`:
  - 다음은 `두 번째` 테이블이다.

![img](/assets/img/sql-sololearn-table operations-03-02.png)

<br>

- For example:

```mysql
SELECT ID, FirstName, LastName, City FROM First
UNION
SELECT ID, FirstName, LastName, City FROM Second;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-table operations-03-03.png)

<br>

> As you can see, the duplicates have been removed.
>
> 보다시피, 중복이 제거되었다.

<br>

#### TIP.

- If your columns don't match exactly across all queries, you can use a `NULL (or any other)` value such as:
  - column이 모든 query에서 정확히 일치하지 않는다면, 다음과 같은 `NULL (또는 다른 값)` 값을 사용할 수 있다.

```mysql
SELECT FirstName, LastName, Company FROM businessContacts
UNION
SELECT FirstName, LastName, NULL FROM otherContacts;
```

<br>

> The UNION operator is used to combine the result-sets of two or more SELECT statements.
>
> UNION 연산자는 두 개 이상 SELECT 문의 result-set을 결합하는 데 사용된다.

------

<br>

### UNION ALL

###### UNION ALL 연산자

<br>

- `UNION ALL` selects all rows from each table and combines them into a single table.
  - `UNION ALL`은 각 테이블의 모든 row를 선택하고, 하나의 테이블로 결합한다.

<br>

- The following SQL statement uses UNION ALL to select data from the `First` and `Second` tables:
  - 다음 SQL 문은 UNION ALL을 사용해서 `First`와 `Second` 테이블의 데이터를 선택한다.

```mysql
SELECT ID, FirstName, LastName, City FROM First
UNION ALL
SELECT ID, FirstName, LastName, City FROM Second;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-table operations-03-04.png)

<br>

> As you can see, the result set includes the duplicate rows as well.
>
> 보다시피, result set에는 중복 row도 포함된다.

------

<br>

### QUIZ

- Drag and drop from the options below to select name, cost, and bids from the "items" table.
  - "items" 테이블에서 name, cost, bids를 선택해라.
- Select only those items whose bids are greater than 123.
  - bids가 123보다 큰 item만 선택한다.

```mysql
SELECT name, cost, bids FROM items
WHERE bids > 123;
```

<br>

- To perform a union operation:
  - UNION 연산을 수행하려면,

> `columns in queries must be the same`
>
> query의 column이 동일해야 한다

<br>

- Type in the command to unite the query results without removing the duplicates.
  - 중복을 제거하지 않고 query 결과를 통합하는 명령어는 무엇인가?

> `UNION ALL`

<br>