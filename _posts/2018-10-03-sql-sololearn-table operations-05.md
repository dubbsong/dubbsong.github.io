---
layout: post
title: "(JOIN, Table Operations 05) UPDATE & DELETE 문"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

### Updating Data

###### 데이터 업데이트하기

<br>

- The `UPDATE` statement allows us to alter data in the table.
  - `UPDATE` 문을 사용해서 테이블의 데이터를 변경할 수 있다.

<br>

- The basic syntax of an UPDATE query with a WHERE clause is as follows:
  - UPDATE query의 기본 구문은 다음과 같다.

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

<br>

- You specify the column and its new value in a comma-separated list after the `SET` keyword.
  - `SET` 키워드에 쉼표로 구분된 리스트로 column과 새 값을 지정한다.

<br>

> If you omit the WHERE clause, `all` records in the table will be updated.
>
> WHERE 절을 생략하면, 테이블의 `모든` 레코드가 업데이트된다.

<br>

<br>

- Consider the following table called "Employees":
  - "Employees" 테이블을 살펴보자.

![img](/assets/img/sql-sololearn-table operations-05-01.png)

<br>

- To update John's salary, we can use the following query:
  - John의 급여를 업데이트하기 위해 다음 query를 사용할 수 있다.

```mysql
UPDATE Employees SET Salary = 5000 WHERE ID = 1;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-table operations-05-02.png)

------

<br>

### Updating Multiple Columns

###### 여러 Column 업데이트하기

<br>

- It is also possible to UPDATE multiple columns at the same time by comma-separating them:
  - 여러 column을 쉼표로 구분해서 동시에 업데이트할 수도 있다.

```mysql
UPDATE Employees SET Salary = 5000, FirstName = 'Robert' WHERE ID = 1;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-table operations-05-03.png)

<br>

> You can specify the column order any way you like in the SET clause.
>
> SET 절에서 column 순서를 원하는 식으로 지정할 수 있다.

------

<br>

### Deleting Data

###### 데이터 삭제하기

<br>

- The `DELETE` statement is used to remove data from your table.
  - `DELETE` 문은 테이블의 데이터를 제거하는 데 사용된다.
- DELETE queries work much like UPDATE queries.
  - DELETE query는 UPDATE query와 매우 유사하게 작동한다.

```sql
DELETE FROM table_name
WHERE condition;
```

<br>

- For example, you can delete a specific employee from the table:
  - 예를 들어, 테이블에서 특정 직원을 삭제할 수 있다.

```mysql
DELETE FROM Employees WHERE ID = 1;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-table operations-05-04.png)

<br>

> If you omit the WHERE clause, `all` records in the table will be deleted.
>
> WHERE 절을 생략한다면, 테이블의 `모든` 레코드가 삭제된다.

> The DELETE statement removes the data from the table permanently.
>
> DELETE 문은 테이블에서 데이터를 영구히 제거한다.

------

<br>

### QUIZ

- Type in the command used to update a table.
  - 테이블을 업데이트하는 데 사용되는 명령어는 무엇인가?

> `UPDATE`

<br>

- Drag and drop from the options below to update the "students" table by changing the university's value to "Stanford" if the student's name is "John".
  - "students" 테이블에서 학생 이름이 "John"인 경우, university의 값을 "Stanford"로 변경해라.

```mysql
UPDATE students SET university = 'Stanford' WHERE name = 'John';
```

<br>

- Rearrange the code to update the "name" and "age" columns of the "students" table.
  - "students" 테이블의 "name"과 "age" column을 업데이트해라.

```mysql
UPDATE students SET name = 'Peter', age = 32 WHERE id = 147;
```

<br>

- Drag and drop from the options below to delete a row from "people" in which the ids falls in the range of 5 to 10.
  - "people" 테이블에서 id가 5에서 10 사이인 row를 제거해라.

```mysql
DELETE FROM people WHERE id > 5 AND id < 10;
```

<br>