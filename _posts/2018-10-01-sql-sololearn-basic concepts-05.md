---
layout: post
title: "(Basic Concepts 05) DISTINCT & LIMIT 키워드"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

## The DISTINCT Keyword

###### DISTINCT 키워드

<br>

- In situations in which you have multiple duplicate records in a table, it might make more sense to return only unique records, instead of fetching the duplicates.
  - 한 테이블에 여러 중복 record가 있는 경우, 중복 record를 가져오는 대신, 고유한 record만 반환하는 것이 좋다.

<br>

- The SQL `DISTINCT` keyword is used in conjunction with SELECT to eliminate all duplicate records and return only unique ones.
  - SQL `DISTINCT` 키워드는 SELECT와 함께 사용된다.
  - 모든 중복 record를 제거하고, 고유한 record만 반환한다.

<br>

- The basic syntax of `DISTINCT` is as follows:
  - `DISTINCT`의 기본 구문은 다음과 같다.

```mysql
SELECT DISTINCT column_name1, column_name2 FROM table_name;
```

<br>

- See the `customers` table below:
  - 아래 `customers` 테이블을 살펴보자.

![img](/assets/img/sql-sololearn-basic concepts-05-01.png)

<br>

- Note that there are duplicate `City` names.
  - 중복된 `City` 이름이 있다.
- The following SQL statement selects only distinct values from the City column:
  - 다음 SQL 문은 City column에서 고유한 값만 선택한다.

```mysql
SELECT DISTINCT City FROM customers;
```

<br>

- This would produce the following result.
  - 위 코드는 다음 결과를 출력한다.
- Duplicate entries have been removed.
  - 중복된 항목이 제거된다.

![img](/assets/img/sql-sololearn-basic concepts-05-02.png)

<br>

> The DISTINCT keyword only fetches the unique values.
>
> DISTINCT 키워드는 고유한 값만 가져온다.

------

<br>

## The LIMIT Keyword

###### LIMIT 키워드

<br>

- By default, all results that satisfy the conditions specified in the SQL statement are returned.
  - SQL 문에서는 기본적으로 지정된 조건을 만족하는 모든 결과가 반환된다.
- However, sometimes we need to retrieve just a subset of records.
  - 하지만, record의 일부만 검색하는 것이 필요할 때가 있다.
- In MySQL, this is accomplished by using the `LIMIT` keyword.
  - MySQL에서는 `LIMIT` 키워드를 사용해서 이를 수행한다.

<br>

- The syntax for LIMIT is as follows:
  - LIMIT의 구문은 다음과 같다.

```mysql
SELECT column_list FROM table_name LIMIT [number of records];
```

<br>

- For example, we can retrieve the first `five` records from the `customers` table.
  - 예를 들어, `customers` 테이블에서 처음 `5개`의 record를 검색할 수 있다.

```mysql
SELECT ID, FirstName, LastName, City FROM customers LIMIT 5;
```

<br>

- This would produce the following result:
  - 위 코드는 다음 결과를 출력한다.

![img](/assets/img/sql-sololearn-basic concepts-05-03.png)

<br>

> By default, all results that satisfy the conditions specified in the SQL statement are returned.
>
> SQL 문에서는 기본적으로 지정된 조건을 만족하는 모든 결과가 반환된다.

<br>

<br>

- You can also pick up a set of records from a particular `offset`.
  - 특정 `offset`에서 record 집합을 선택할 수도 있다.
- In the following example, we pick up `four` records, starting from the `third` position:
  - 다음 예제는 `세 번째` 위치부터 `4개`의 record를 선택한다.

```mysql
SELECT ID, FirstName, LastName, City FROM customers LIMIT 3, 4;
```

<br>

- This would produce the following result:
  - 위 코드는 다음 결과를 출력한다.

![img](/assets/img/sql-sololearn-basic concepts-05-04.png)

<br>

> The reason that it produces results starting from ID number four, and not three, is that MySQL starts counting from `zero`, meaning that the offset of the first row is 0, not 1.
>
> MySQL은 `0`부터 세기 시작하므로, 첫 번째 row는 1이 아닌 0이다.
>
> 그러므로 ID 숫자가 3이 아닌 4에서 시작하는 결과를 출력한다.

------

<br>

## QUIZ

- Drag and drop from the options below to build a query to get distinct results from the "customers" table.
  - "customers" 테이블에서 distinct 결과를 얻기 위한 query를 작성해라.

```mysql
SELECT DISTINCT state FROM customers;
```

<br>

- Drag and drop from the options below to complete the following statement, which selects five names from "students".
  - "students"에서 5개의 이름을 선택하는 명령문을 작성해라.

```mysql
SELECT name FROM students LIMIT 5;
```

<br>

- Use LIMIT to select the "id" and "name" columns from "customers".
  - LIMIT을 사용해 "customers"에서 "id"와 "name" column을 선택해라.
- Show 12 results, starting from the fifth.
  - 다섯 번째부터 시작해서 12개의 결과를 표시해라.

```mysql
SELECT id, name FROM customers LIMIT 4, 12;
```

<br>