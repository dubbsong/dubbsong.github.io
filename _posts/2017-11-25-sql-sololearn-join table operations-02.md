---
layout: post
title: "02. join 타입 (JOIN, Table Operations)"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com) SQL 번역

<br>

# Types of Join

###### join 타입

<br>

## Custom Names

###### 사용자 정의 이름

<br>

- Custom names can be used for tables as well.
  - 사용자 정의 이름을 테이블에서도 사용할 수 있다.
- You can shorten the join statements by giving the tables "nicknames":
  - 테이블에 "nickname"을 지정해서, join 문을 단축할 수 있다.

```mysql
SELECT ct.ID, ct.Name, ord.Name, ord.Amount
FROM customers AS ct, orders AS ord
WHERE ct.ID=ord.Customer_ID
ORDER BY ct.ID;
```

<br>

> As you can see, we shortened the table names as we used them in our query.
>
> 보다시피, query에서 테이블 이름을 사용하는 것처럼, 테이블 이름을 짧게 했다.

<br>

<br>

- The following are the types of JOIN that can be used in MySQL:
  - 다음은 MySQL에서 사용할 수 있는 JOIN 타입이다.

<br>

> `INNER` JOIN
>
> `LEFT` JOIN
>
> `RIGHT` JOIN

<br>

- `INNER JOIN` is equivalent to JOIN.
  - `INNER JOIN`은 JOIN과 같다.
  - `INNER JOIN`: selects all rows from both tables as long as there is a match between the columns in both tables (두 테이블의 column이 일치하는 양 테이블의 모든 row를 선택한다)
- It returns rows when there is a match between the tables.
  - 테이블 간에 일치하는 것이 있으면 row를 반환한다.

<br>

- Syntax:

```mysql
SELECT column_name(s)
FROM table1 INNER JOIN table2
ON table1.column_name=table2.column_name;
```

<br>

> Note tha `ON` keyword for specifying the inner join condition.
>
> inner join 조건을 지정하려면, `ON` 키워드를 주의해라.

<br>

- The image below demonstrates how `INNER JOIN` works:
  - 아래 이미지는 `INNER JOIN`의 작동 방식을 보여준다.

![sololearn img](/assets/img/sololearn-sql-join table operations-02-01.png)

<br>

> Only the records matching the join condition are returned.
>
> join 조건과 일치하는 레코드만 반환한다.

------

<br>

## LEFT JOIN

- The `LEFT JOIN` returns all rows from the left table, even if there are no matches in the right table.
  - `LEFT JOIN`은 오른쪽 테이블에 일치하는 것이 없더라도, 왼쪽 테이블의 모든 row를 반환한다.
  - `LEFT JOIN`: returns all rows from the left table, with the matching rows in the right table (왼쪽 테이블에서 모든 row를 반환하고, 오른쪽 테이블에서 일치하는 row를 반환한다)

<br>

- This means that if there are no matches for the `ON` clause in the table on the right, the join will still return the rows from the first table in the result.
  - 즉, 오른쪽 테이블의 `ON` 절과 일치하는 것이 없으면, join은 여전히 첫 번째 테이블의 결과에서 row를 반환한다.

<br>

- The basic syntax of `LEFT JOIN` is as follows:
  - `LEFT JOIN`의 기본 문법은 다음과 같다.

```mysql
SELECT table1.column1, table2.column2...
FROM table1 LEFT OUTER JOIN table2
ON table1.column_name = table2.column_name;
```

<br>

> The `OUTER` keyword is optional, and can be omitted.
>
> `OUTER` 키워드는 선택적이며, 생략할 수 있다.

<br>

- The image below demonstrates how `LEFT JOIN` works:
  - 아래 이미지는 `LEFT JOIN`의 작동 방식을 보여준다.

![sololearn img](/assets/img/sololearn-sql-join table operations-02-02.png)

<br>

- Consider the following tables:
  - 다음 표를 참조해라.

<br>

- customers:

![sololearn img](/assets/img/sololearn-sql-join table operations-02-03.png)

<br>

- items:

![sololearn img](/assets/img/sololearn-sql-join table operations-02-04.png)

<br>

- The following SQL statement will return all `customers`, and the `items` they might have:
  - 다음 SQL 문은 모든 `customers`와 고객이 가질 수 있는 `items`를 반환한다.

```mysql
SELECT customers.Name, items.Name
FROM customers LEFT OUTER JOIN items
ON customers.ID = items.Seller_id;
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-sql-join table operations-02-05.png)

<br>

- The result set contains all the rows from the left table and matching data from the right table.
  - 결과 집합에는 왼쪽 테이블의 모든 row와, 오른쪽 테이블의 일치하는 데이터가 포함된다.

<br>

> If no match is found for a particular row, `NULL` is returned.
>
> 특정 row에 일치하는 것이 없으면, `NULL`이 반환된다.
>
> `NULL`: An absence of value (값의 부재)

------

<br>

## RIGHT JOIN

- The `RIGHT JOIN` returns all rows from the right table, even if there are no matches in the left table.
  - `RIGHT JOIN`은 왼쪽 테이블에 일치하는 것이 없더라도, 오른쪽 테이블의 모든 row를 반환한다.
  - `RIGHT JOIN`: returns all rows from the right table, with the matching rows in the left table (왼쪽 테이블에서 일치하는 row와 함께 오른쪽 테이블에서 모든 row를 반환한다)

![sololearn img](/assets/img/sololearn-sql-join table operations-02-06.png)

<br>

- The basic syntax of `RIGHT JOIN` is as follows:
  - `RIGHT JOIN`의 기본 문법은 다음과 같다.

```mysql
SELECT table1.column1, table2.column2...
FROM table1 RIGHT OUTER JOIN table2
ON table1.column_name = table2.column_name;
```

<br>

> Again, the `OUTER` keyword is optional, and can be omitted.
>
> `OUTER` 키워드는 선택적이며, 생략될 수 있다.

<br>

- Consider the same example from our previous lesson, but this time with a `RIGHT JOIN`:
  - 이전 레슨과 동일한 예제를 고려해보자.
  - 이번에는 `RIGHT JOIN`을 사용하자.

```mysql
SELECT customers.Name, items.Name FROM customers
RIGHT JOIN items ON customers.ID = items.Seller_id;
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-sql-join table operations-02-07.png)

<br>

- The `RIGHT JOIN` returns all the rows from the right table (items), even if there are no matches in the left table (customers).
  - `RIGHT JOIN`은 왼쪽 테이블(customers)에서 일치하는 것이 없더라도, 오른쪽 테이블(items)의 모든 row를 반환한다.

<br>

> There are other types of joins in the SQL language, but they are not supported by MySQL
>
> SQL 언어에는 다른 join 타입이 있지만, MySQL에서는 지원하지 않는다.

------

<br>

## QUIZ

- Fill in the blanks to select item names and names of customers who bought the items.
  - 항목을 구입한 고객의 이름과 항목 이름을 선택해라.
- Use custom names to shorten the statement.
  - 사용자 정의 이름을 사용해서 명령문을 단축해라.

```mysql
SELECT ct.name, it.name
FROM customers AS ct, items AS it
WHERE it.seller_id=ct.id;
```

<br>

- Rearrange the query to select the names of students and the names of the universities where those students study.
  - 학생들의 이름과, 학생들이 공부하는 대학의 이름을 선택해라.

```mysql
SELECT students.name, universities.name
FROM students, universities
WHERE students.university_id=universities.id
```

<br>

- Drag and drop from the options below to outer join the table "items" with "customers".
  - 테이블 "items"와 "customers"를 outer join 해라.

```mysql
SELECT customers.name, items.name
FROM customers
LEFT OUTER JOIN items
ON customers.id = seller_id
```

<br>

- Rearrange the code to select student names and all university names (use right join to show all university names).
  - 학생 이름과 모든 대학 이름을 선택해라.
  - (모든 대학 이름을 표시하려면, right join을 사용해라)

```mysql
SELECT students.names, universities.names
FROM students
RIGHT OUTER JOIN universities
ON students.university_id = universities.id
```

<br>
