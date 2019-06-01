---
layout: post
title: "(Basic Concepts 06) 결과 정렬하기"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

### Fully Qualified Names

###### 정규화된 이름

<br>

- In SQL, you can provide the table name prior to the column name, by separating them with a `dot`.
  - SQL에서는, column 이름 앞에 `점`으로 구분해서 테이블 이름을 제공할 수 있다.
- The following statements are equivalent:
  - 다음 명령문들은 동일하다.

```mysql
SELECT City FROM customers;

SELECT customers.City FROM customers;
```

<br>

- The term for the above-mentioned syntax is called the `"fully qualified name"` of that column.
  - 위에서 언급한 구문의 용어를 해당 column의 `"정규화된 이름"`이라고 한다.

<br>

> This form of writing is especially useful when working with multiple tables that may share the same column names.
>
> 위와 같은 작성 서식은, 동일한 column 이름을 공유할 수 있는 여러 개의 테이블로 작업할 때 특히 유용하다.

------

<br>

### ORDER BY Keyword

###### ORDER BY 키워드

<br>

- `ORDER BY` is used with SELECT to `sort` the returned data.
  - `ORDER BY`는 반환되는 데이터를 `정렬`한다.

<br>

- The following example sorts our `customers` table by the *FirstName* column.
  - 다음 예제에서는 `customers` 테이블을 *FirstName* column으로 정렬한다.

```mysql
SELECT * FROM customers
ORDER BY FirstName;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-basic concepts-06-01.png)

<br>

- As you can see, the rows are ordered `alphabetically` by the `FirstName` column.
  - 보다시피, row는 `FirstName` column의 `ABC순`으로 정렬된다.

<br>

> By default, the ORDER BY keyword sorts the results in `ascending order`.
>
> 기본적으로 ORDER BY 키워드는 결과를 `오름차순`으로 정렬한다.

------

<br>

### Sorting Multiple Columns

###### 여러 column 정렬하기

<br>

- ORDER BY can sort retrieved data by multiple columns.
  - ORDER BY는 검색된 데이터를 여러 column으로 정렬할 수 있다.
- When using ORDER BY with more than one column, separate the list of columns to follow ORDER BY with `commas`.
  - 둘 이상의 column과 함께 ORDER BY를 사용하는 경우, ORDER BY 뒤에 오는 column 리스트를 `쉼표`로 구분한다.

<br>

- Here is the `customers` table, showing the following records:
  - 다음은 `customers` 테이블이다.

![img](/assets/img/sql-sololearn-basic concepts-06-02.png)

<br>

- To order by `LastName` and `Age`:
  - `LastName`과 `Age`로 정렬해보자.

```mysql
SELECT * FROM customers ORDER BY LastName, Age;
```

<br>

- This `ORDER BY` statement returns the following result:
  - 위 `ORDER BY` 문은 다음 결과를 반환한다.

![img](/assets/img/sql-sololearn-basic concepts-06-03.png)

<br>

- As we have two `Smith`s, they will be ordered by the `Age` column in ascending order.
  - `Smith`가 두 명이므로, `Age` column에 따라 오름차순으로 정렬된다.

------

<br>

### QUIZ

- Fill in the blanks to select the "address" from "customers", using the fully qualified name for the "address" column.
  - "address" column에 정규화된 이름을 사용해서, "customers"의 "address"를 선택해라.

```mysql
SELECT customers.address FROM customers;
```

<br>

- Build a query to select "name" and "city" from the "people" table, and order by the "id".
  - "people" 테이블의 "name"과 "city"를 선택하고, "id"로 정렬해라.

```mysql
SELECT name, city FROM people ORDER BY id;
```

<br>

- Fill in the blanks to order the query results by "name", and then by "state".
  - query 결과를 "name"으로 정렬한 다음, "state"로 정렬해라.

```mysql
SELECT name, state, address FROM customers ORDER BY name, state;
```

<br>