---
layout: post
title: "04. INSERT 문 (JOIN, Table Operations)"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com) SQL 번역

<br>

# The INSERT Statement

###### INSERT 문

------

<br>

<br>

## Inserting Data

###### 데이터 삽입하기

<br>

- SQL tables store data in rows, one row after another.
  - SQL 테이블은 데이터를 한 row씩 여러 row에 저장한다.
- The `INSERT INTO` statement is used to add `new rows` of data to a table in the database.
  - `INSERT INTO` 문은 데이터베이스의 테이블에 `새로운 row` 데이터를 추가하는 데 사용된다.
  - `INSERT INTO`: is used to insert new records in a table (테이블에 새 레코드를 삽입하는 데 사용된다)
- The SQL `INSERT INTO` syntax is as follows:
  - SQL `INSERT INTO` 문법은 다음과 같다.

```mysql
INSERT INTO table_name
VALUES (value1, value2, value3, ...);
```

<br>

> Make sure the order of the values is in the same order as the columns in the table.
>
> 값의 순서가 테이블의 column과 동일한 순서인지 확인해라.

<br>

- Consider the following `Employees` table:
  - 다음 `Employees` 테이블을 고려해라.

![sololearn img](/assets/img/sololearn-sql-join table operations-04-01.png)

<br>

- Use the following SQL statement to insert a new row.
  - 다음 SQL 문을 사용해서 새로운 row를 삽입해라.

```mysql
INSERT INTO Employees
VALUES (8, 'Anthony', 'Young', 35);
```

<br>

- The values are comma-separated and their order corresponds to the columns in the table.
  - 값은 쉼표로 구분되며, 순서는 테이블의 column에 해당한다.

<br>

- Result:

![sololearn img](/assets/img/sololearn-sql-join table operations-04-02.png)

<br>

> When inserting records into a table using the SQL INSERT statement, you must provide a value for every column that does not have a default value, or does not support NULL.
>
> SQL INSERT 문을 사용해서 테이블에 레코드를 삽입할 때, 기본값이 없거나 NULL을 지원하지 않는 모든 column에 값을 제공해야 한다.

------

<br>

## Inserting Data

###### 데이터 삽입하기

<br>

- Alternatively, you can specify the table's column names in the `INSERT INTO` statement:
  - 대안이 되는 것으로, `INSERT INTO` 문에서 테이블의 column 이름을 지정할 수 있다.

```mysql
INSERT INTO table_name (column1, column2, column3, ..., columnN)
VALUES (value1, value2, value3, ...valueN);
```

<br>

- column1, column2, ..., columnN are the names of the columns that you want to insert data into.
  - column1, column2, ..., columnN은 데이터를 삽입하려는 column의 이름이다.

```mysql
INSERT INTO Employees (ID, FirstName, LastName, Age)
VALUES (8, 'Anthony', 'Young', 35);
```

<br>

- This will insert the data into the corresponding columns:
  - 이렇게 하면, 데이터가 해당 column에 삽입된다.

![sololearn img](/assets/img/sololearn-sql-join table operations-04-03.png)

<br>

> You can specify your own column order, as long as the values are specified in the same order as the columns.
>
> 값이 column과 동일한 순서로 지정되어 있는 한, 자신의 column 순서를 지정할 수 있다.

<br>

<br>

- It is also possible to insert data into `specific` columns only.
  - `특정` column에만 데이터를 삽입할 수도 있다.

```mysql
INSERT INTO Employees (ID, FirstName, LastName)
VALUES (9, 'Samuel', 'Clark');
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-sql-join table operations-04-04.png)

<br>

> The *Age* column for that row automatically became `0`, as that is its default value.
>
> 해당 row의 *Age* column은 기본값으로 자동으로 `0`이 된다.

------

<br>

## QUIZ

- Drag and drop from the options below to insert the data into the "students" table.
  - "students" 테이블에 데이터를 삽입해라.

```mysql
INSERT INTO students
VALUES ('John Smith', 'MIT');
```

<br>

- Rearrange the code to insert the data into the "student" table, using actual column names.
  - 실제 column 이름을 사용해서 "student" 테이블에 데이터를 삽입하도록 코드를 재정렬해라.

```mysql
INSERT INTO students (name, university)
VALUES ('Peter Parker', 'Stanford');
```

<br>

- When inserting data into a table:
  - 테이블에 데이터를 삽입할 때:

> `We don't have to insert values for all columns in the table`
>
> `테이블의 모든 column에 값을 삽입할 필요가 없다`

<br>
