---
layout: post
title: "(Basic 07) Module 1 Quiz"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

## QUIZ

- A database consists of:
  - 데이터베이스는 ...로 구성된다.

> `Tables`

<br>

- Drag and drop from the options below to list the table names.
  - 테이블 이름을 나열해라.

```mysql
SHOW TABLES;
```

<br>

- Why use primary keys?
  - 왜 primary key를 사용하는가?

> `To guarantee the uniqueness of a row`
>
> row의 고유성을 보장하기 위해

<br>

- Drag and drop from the options below to select distinct names from the "students" table, ordered by name.
  - "students" 테이블에서 distinct 이름을 선택하고, 이름순으로 정렬해라.

```mysql
SELECT DISTINCT name
FROM students
ORDER BY name;
```

<br>