---
layout: post
title: "(JOIN, Table Operations 08) ALTER, DROP, RENAME"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

### ALTER TABLE

###### ALTER TABLE 명령어

<br>

- The `ALTER TABLE` command is used to add, delete, or modify columns in an existing table.
  - `ALTER TABLE` 명령어는 기존 테이블의 column을 추가, 삭제 또는 수정하는 데 사용된다.
- You would also use the ALTER TABLE command to add and drop various constraints on an existing table.
  - 또한 기존 테이블에 다양한 제한 조건을 추가 및 제거할 수 있다.

<br>

- Consider the following table called `People`:
  - `People`이라는 테이블을 살펴보자.

![img](/assets/img/sql-sololearn-table operations-08-01.png)

<br>

- The following SQL code adds a new column named `DateOfBirth`:
  - 다음 SQL 코드는 `DateOfBirth`라는 새 column을 추가한다.

```mysql
ALTER TABLE People ADD DateOfBirth date;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-table operations-08-02.png)

<br>

> All rows will have the default value in the newly added column, which, in this case, is NULL.
>
> 모든 row는 새로 추가된 column에 기본 값을 가진다.
>
> 위의 경우에는 NULL을 가진다.

------

<br>

### Dropping

###### 제거하기

<br>

- The following SQL code demonstrates how to delete the column named *DateOfBirth* in the People table.
  - 다음 SQL 코드는, People 테이블에서 *DateOfBirth*라는 column을 어떻게 삭제하는지 보여준다.

```mysql
ALTER TABLE People DROP COLUMN DateOfBirth;
```

<br>

- The People table will now look like this:
  - People 테이블은 이제 다음과 같다.

![img](/assets/img/sql-sololearn-table operations-08-03.png)

<br>

> The column, along with all of its data, will be completely removed from the table.
>
> column은 모든 데이터와 함께 테이블에서 완전히 제거된다.

<br>

- To delete the entire table, use the `DROP TABLE` command:
  - 전체 테이블을 삭제하기 위해, `DROP TABLE` 명령어를 사용한다.

```mysql
DROP TABLE People;
```

<br>

> Be careful when dropping a table.
>
> 테이블을 제거할 때 주의한다.

> Deleting a table will result in the complete loss of the information stored in the table.
>
> 테이블을 삭제하면, 테이블에 저장된 정보가 완전히 사라진다.

------

<br>

### Renaming

###### 이름 변경하기

<br>

- The ALTER TABLE command is also used to rename columns:
  - ALTER TABLE 명령어는 column의 이름을 변경하는 데에도 사용된다.

```mysql
ALTER TABLE People
CHANGE FirstName name varchar(100);
```

<br>

- Result:

![img](/assets/img/sql-sololearn-table operations-08-04.png)

<br>

- This query will rename the column called FirstName to name.
  - 위의 query는 FirstName이라는 column 이름을 name으로 변경한다.

<br>

- You can rename the entire table using the `RENAME` command:
  - `RENAME` 명령어를 사용해서 전체 테이블의 이름을 변경할 수 있다.

```mysql
RENAME TABLE People TO Users;
```

<br>

- This will rename the table People to Users.
  - 위의 query는 People 테이블의 이름을 Users로 변경한다.

------

<br>

### QUIZ

- Drag and drop from the options below to add a new column entitled "specialty" to the table "students".
  - "students" 테이블에 "specialty"라는 제목의 새 column을 추가해라.

```mysql
ALTER TABLE students ADD specialty varchar(50);
```

<br>

- Which choice is the correct command for deleting a table?
  - 테이블을 삭제하기 위한 명령어는 무엇인가?

> `DROP TABLE`

<br>

- Drag and drop from the options below to rename the table "people" as "humans".
  - "people" 테이블의 이름을 "humans"로 변경해라.

```mysql
RENAME TABLE people TO humans;
```

<br> 