---
layout: post
title: "(JOIN, Table Operations 07) NOT NULL & AUTO_INCREMENT"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

### SQL Constraints

###### SQL 제한 조건

<br>

- SQL `constraints` are used to specify rules for table data.
  - SQL `제한 조건`은 테이블 데이터에 대한 규칙을 지정하는 데 사용된다.

<br>

- The following are commonly used SQL constraints:
  - 다음은 일반적으로 사용되는 SQL 제한 조건들이다.

<br>

> `NOT NULL`
>
> Indicates that a column cannot contain any NULL value.
>
> column에 NULL 값이 포함될 수 없음을 나타낸다.

> `UNIQUE`
>
> Does not allow to insert a duplicate value in a column.
>
> column에 중복 값을 삽입할 수 없다.
>
> The UNIQUE constraint maintains the uniqueness of a column in a table.
>
> UNIQUE 제한 조건은 테이블에서 column의 고유성을 유지한다.
>
> More than one UNIQUE column can be used in a table.
>
> 테이블에서 하나 이상의 UNIQUE column을 사용할 수 있다.

> `PRIMARY KEY`
>
> Enforces the table to accept unique data for a specific column and this constraint create a unique index for accessing the table faster.
>
> 테이블이 특정 column에 대해 고유한 데이터를 받아들이도록 강제한다.
>
> 이 제한 조건은 테이블에 빨리 액세스하기 위한 고유 인덱스를 생성한다.

> `CHECK`
>
> Determines whether the value is valid or not from a logical expression.
>
> 값이 논리 표현식에서 유효한지 여부를 판단한다.

> `DEFAULT`
>
> While inserting data into a table, if no value is supplied to a column, then the column gets the value set as DEFAULT.
>
> 테이블에 데이터를 삽입하는 동안 column에 값이 제공되지 않으면, column은 DEFAULT로 설정된 값을 가져온다.

<br>

- For example, the following means that the `name` column disallows NULL values.
  - 예를 들어, 다음은 `name` column이 NULL 값을 허용하지 않음을 의미한다.

```mysql
name varchar(100) NOT NULL
```

<br>

> During table creation, specify column level constraint(s) after the data type of that column.
>
> 테이블을 생성할 때, 해당 column의 데이터 타입 뒤에 column level 제한 조건을 지정한다.

------

<br>

### AUTO_INCREMENT

###### 자동 증가

<br>

- AUTO_INCREMENT allows a unique number to be generated when a new record is inserted into a table.
  - 자동 증가는 새 레코드가 테이블에 삽입될 때 고유 번호가 생성되도록 한다.

- Often, we would like the value of the primary key field to be created automatically every time a new record is inserted.
  - 새 레코드가 삽입될 때마다, primary key field의 값이 자동으로 생성된다.

- By default, the starting value for `AUTO_INCREMENT` is 1, and it will increment by 1 for each new record.
  - 기본적으로 `AUTO_INCREMENT`의 시작 값은 1이다.
  - 새 레코드마다 1씩 증가한다.

<br>

- Let's set the UserID field to be a primary key that automatically generates a new value:
  - UserID field를 자동으로 새 값을 생성하는 primary key로 설정해보자.

```mysql
UserID int NOT NULL AUTO_INCREMENT
PRIMARY KEY(UserID)
```

------

<br>

### Using Constraints

###### 제한 조건 사용하기

<br>

- The example below demonstrates how to create a table using constraints.
  - 아래 예제는 제한 조건을 사용해서 테이블을 생성하는 방법을 보여준다.

```mysql
CREATE TABLE Users (
  id int NOT NULL AUTO_INCREMENT,
  username varchar(40) NOT NULL,
  password varchar(10) NOT NULL,
  PRIMARY KEY(id)
);
```

<br>

- Result:

![img](/assets/img/sql-sololearn-table operations-07-01.png)

<br>

- The following SQL enforces that the "id", "username", and "password" columns do not accept NULL values.
  - 위 SQL은 "id", "username", "password" column이 NULL 값을 허용하지 않도록 강제한다.
- We also define the "id" column to be an auto-increment primary key field.
  - 또한 "id" column을 자동 증가 primary key field로 정의한다.

<br>

> When inserting a new record into the Users table, it's not necessary to specify a value for the id column.
>
> Users 테이블에 새 레코드를 삽입할 때, id column에 값을 지정할 필요가 없다.

> A unique new value will be added automatically.
>
> 고유한 새 값이 자동으로 추가된다.

------

<br>

### QUIZ

- Fill in the missing parts so that the column "username" disallows empty values.
  - "username" column에서 빈 값을 허용하지 않도록 해라.

```mysql
username varchar(50) NOT NULL
```

<br>

- Drag and drop from the options below to have the "id" column auto increment by one each time a new row is inserted.
  - 새 row가 삽입될 때마다, "id" column이 자동으로 하나씩 증가하도록 해라.

```mysql
id int NOT NULL AUTO_INCREMENT
```

<br>

- Drag and drop from the options below to create a table with an auto incremented and not empty primary key "id".
  - 자동으로 증가하고, "id"가 비어 있지 않은 primary key인 테이블을 생성해라.

```mysql
CREATE TABLE test (
  id int NOT NULL AUTO_INCREMENT,
  name varchar(30) NOT NULL,
  PRIMARY KEY(id)
);
```

<br>