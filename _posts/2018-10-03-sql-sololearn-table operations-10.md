---
layout: post
title: "(JOIN, Table Operations 10) QUIZ"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

### QUIZ

- Rearrange to select all student names and university names (use left join to show all student names).
  - 모든 학생 이름과 대학 이름을 선택해라.
  - left join을 사용해서 모든 학생 이름을 보여준다.

```mysql
SELECT students.names, universities.names FROM students
LEFT OUTER JOIN universities
ON students.university_id = universities.id;
```

<br>

- Drag and drop from the options below to insert a data item into the "people" table.
  - "people" 테이블에 데이터 item을 삽입해라.

```mysql
INSERT INTO people
VALUES ('John Smith', '1', 22);
```

<br>

- Drag and drop from the options below to update the "people" table.
  - "people" 테이블을 업데이트해라.

```mysql
UPDATE people
SET name = 'Jordan'
WHERE id = 147;
```

<br>

- Fill in the blanks to create a table with two columns: "id" as a primary key integer, and "name" of type varchar.
  - 두 column이 있는 테이블을 생성해라.
  - "id"를 정수 primary key로, "name"을 varchar 타입으로 한다.

```mysql
CREATE TABLE (
  id int,
  name varchar(30),
  PRIMARY KEY(id)
);
```

<br>

- Rearrange to remove the column "age" from the "people" table.
  - "people" 테이블의 "age" column을 제거해라.

```mysql
ALTER TABLE people DROP COLUMN age;
```

<br>

- Which choice is the correct command for changing the name of a table?
  - 테이블의 이름을 변경하는 명령어는 무엇인가?

> `RENAME`

<br>

- Drag and drop from the options below to create a view named "most_abs" for the students with the greatest number of absences.
  - 가장 많은 결석을 한 학생에 대한 "most_abs"라는 view를 생성해라.

```mysql
CREATE VIEW most_abs AS
SELECT id, name, absences FROM students
ORDER BY absences DESC LIMIT 10;
```

<br>

- Drag and drop from the options below to delete the table "students" from the database.
  - 데이터베이스의 "students" 테이블을 삭제해라.

```mysql
DROP TABLE students;
```

<br>

- Drag and drop from the options below to remove the column "temp" from the table "students".
  - "students" 테이블의 "temp" column을 제거해라.

```mysql
ALTER TABLE students
DROP COLUMN temp;
```

<br>