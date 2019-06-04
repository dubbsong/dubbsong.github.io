---
layout: post
title: "(JOIN, Table Operations 02) JOIN 타입"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

### Custom Names

###### 사용자 정의 이름

<br>

- Custom names can be used for tables as well.
  - 테이블에서도 사용자 정의 이름을 사용할 수 있다.
- You can shorten the join statements by giving the tables "nicknames":
  - 테이블에 "닉네임"을 지정해서 JOIN 문을 단축할 수 있다.

```mysql
SELECT ct.ID, ct.Name, ord.Name, ord.Amount
FROM customers AS ct, orders AS ord
WHERE ct.ID = ord.Customer_ID
ORDER BY ct.ID;
```

<br>

> As you can see, we shortened the table names as we used them in our query.
>
> 보다시피, query에서 테이블 이름을 사용하는 것처럼 테이블 이름을 단축했다.

<br>

<br>

- The following are the types of JOIN that can be used in MySQL:
  - 다음은 MySQL에서 사용할 수 있는 JOIN 타입들이다.

<br>

1. `INNER` JOIN
2. `LEFT` JOIN
3. `RIGHT` JOIN

<br>

- `INNER` JOIN is equivalent to JOIN.
  - `INNER` JOIN은 JOIN과 동일하다.
- It returns rows when there is a match between the tables.
  - 테이블 간 일치가 있을 때 row를 반환한다.

<br>

- Syntax:

```sql
SELECT column_name(s)
FROM table1 INNER JOIN table2
ON table1.column_name = table2.column_name;
```

<br>

> Note the `ON` keyword for specifying the inner join condition.
>
> INNER JOIN 조건을 지정하기 위해 `ON` 키워드를 사용한다.

<br>

- The image below demonstrates how INNER JOIN works:
  - 아래 이미지는 INNER JOIN의 작동 방식을 보여준다.

![img](/assets/img/sql-sololearn-table operations-02-01.png)

<br>

> Only the records matching the join condition are returned.
>
> JOIN 조건과 일치하는 레코드만 반환된다.

------

<br>

### LEFT JOIN

###### LEFT JOIN

<br>

- The `LEFT JOIN` returns all rows from the left table, even if there are no matches in the right table.
  - `LEFT JOIN`은 오른쪽 테이블에 일치하는 것이 없더라도, 왼쪽 테이블의 모든 row를 반환한다.

- This means that if there are no matches for the `ON` clause in the table on the right, the join will still return the rows from the first table in the result.
  - 즉, 오른쪽 테이블의 `ON` 절과 일치하는 것이 없다면, JOIN은 여전히 결과의 첫 번째 테이블에서 row를 반환한다.

<br>

- The basic syntax of LEFT JOIN is as follows:
  - LEFT JOIN의 기본 구문은 다음과 같다.

```sql
SELECT table1.column1, table2.column2...
FROM table1 LEFT OUTER JOIN table2
ON table1.column_name = table2.column_name;
```

<br>

> The `OUTER` keyword is optional, and can be omitted.
>
> `OUTER` 키워드는 선택 사항이며, 생략할 수 있다.

<br>

- The image below demonstrates how LEFT JOIN works:
  - 아래 이미지는 LEFT JOIN의 작동 방식을 보여준다.

![img](/assets/img/sql-sololearn-table operations-02-02.png)

<br>

- Consider the following tables:
  - 다음 테이블을 살펴보자.
- customers table:

![img](/assets/img/sql-sololearn-table operations-02-03.png)

<br>

- items table:

![img](/assets/img/sql-sololearn-table operations-02-04.png)

<br>

- The following SQL statement will return all `customers`, and the `items` they might have:
  - 다음 SQL 문은 모든 `customers`와, customers가 가질 수 있는 `item`을 반환한다.

```mysql
SELECT customers.Name, items.Name
FROM customers LEFT OUTER JOIN items
ON customers.ID = items.Seller_id;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-table operations-02-05.png)

<br>

- The result set contains all the rows from the left table and matching data from the right table.
  - result set에는 왼쪽 테이블의 모든 row와, 오른쪽 테이블의 일치하는 데이터가 포함된다.

<br>

> If no match is found for a particular row, `NULL` is returned.
>
> 특정 row에 일치하는 것이 없다면, `NULL`이 반환된다.

------

<br>

### RIGHT JOIN

###### RIGHT JOIN

<br>

- The `RIGHT JOIN` returns all rows from the right table, even if there are no matches in the left table.
  - `RIGHT JOIN`은 왼쪽 테이블에 일치하는 항목이 없더라도, 오른쪽 테이블의 모든 row를 반환한다.

![img](/assets/img/sql-sololearn-table operations-02-06.png)

<br>

- The basic syntax of RIGHT JOIN is as follows:
  - RIGHT JOIN의 기본 구문은 다음과 같다.

```sql
SELECT table1.column1, table2.column2...
FROM table1 RIGHT OUTER JOIN table2
ON table1.column_name = table2.column_name;
```

<br>

> Again, the `OUTER` keyword is optional, and can be omitted.
>
> `OUTER` 키워드는 선택 사항이며, 생략할 수 있다.

<br>

- Consider the same example from our previous lesson, but this time with a RIGHT JOIN:
  - 이전 레슨과 동일한 예제를 살펴보자.
  - 하지만 이번에는 RIGHT JOIN을 사용한다.

```mysql
SELECT customers.Name, items.Name
FROM customers
RIGHT JOIN items ON customers.ID = items.Seller_id;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-table operations-02-07.png)

<br>

- The RIGHT JOIN returns all the rows from the right table (items), even if there are no matches in the left table (customers).
  - RIGHT JOIN은 왼쪽 테이블(customers)에 일치하는 것이 없더라도, 오른쪽 테이블(items)의 모든 row를 반환한다.

<br>

> There are other types of joins in the SQL language, but they are not supported by MySQL.
>
> SQL 언어에는 다른 JOIN 타입이 있지만, MySQL에서는 지원하지 않는다.

------

<br>

### QUIZ

- Fill in the blanks to select item names and names of customers who bought the items.
  - item을 구매한 고객의 이름과 item의 이름을 선택해라.
- Use custom names to shorten the statement.
  - 사용자 정의 이름을 사용해서 명령문을 단축해라.

```mysql
SELECT ct.name, it.name
FROM customers AS ct, items AS it
WHERE it.seller_id = ct.id;
```

<br>

- Rearrange the query to select the names of students and the names of the universities where those students study.
  - 학생의 이름과 그 학생이 공부하는 대학의 이름을 선택해라.

```mysql
SELECT students.name, universities.name
FROM students, universities
WHERE students.university_id = universities.id;
```

<br>

- Drag and drop from the options below to outer join the table "items" with "customers".
  - "items" 테이블을 "customers"로 OUTER JOIN 해라.

```mysql
SELECT customers.name, items.name
FROM customers
LEFT OUTER JOIN items
ON customers.id = seller_id;
```

<br>

- Rearrange the code to select student names and all university names (use right join to show all university names).
  - 학생 이름과 모든 대학의 이름을 선택해라.
  - (모든 대학의 이름을 나타내기 위해 RIGHT JOIN을 사용한다)

```mysql
SELECT students.names, universities.names
FROM students
RIGHT OUTER JOIN universities
ON students.university_id = universities.id;
```

<br>