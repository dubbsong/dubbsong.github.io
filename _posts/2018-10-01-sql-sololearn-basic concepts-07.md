---
layout: post
title: "(Basic Concepts 07) QUIZ"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

### QUIZ

- A database consists of:
  - 데이터베이스는 ...로 구성된다.

> `tables`

<br>

- Drag and drop from the options below to list the table names.
  - 테이블 이름을 나열해라.

```mysql
SHOW TABLES;
```

<br>

- Why use primary keys?
  - primary key를 사용하는 이유는 무엇인가?

> `To guarantee the uniqueness of a row`
>
> row의 고유성을 보장하기 위해

<br>

- Drag and drop from the options below to select distinct names from the "students" table, ordered by name.
  - "students" 테이블에서 고유한 name을 선택한 다음, name으로 정렬해라.

```mysql
SELECT DISTINCT name FROM students ORDER BY name;
```

<br>