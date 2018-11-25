---
layout: post
title: "(Filtering, Functions, Subqueries 08) Module 2 Quiz"
categories: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

## QUIZ

- Fill in the blanks to select all values from the "students" table in which the field "university" equals "MIT".
  - "students" 테이블에서 "university" field가 "MIT"인 모든 값을 선택해라.

```mysql
SELECT * FROM students
WHERE university = 'MIT';
```

<br>

- Rearrange the code to select students from MIT and Stanford, and order the results by the "university" column.
  - MIT와 Stanford에서 students를 선택하고, "university" column에 따라 결과를 정렬해라.

```mysql
SELECT name, university
FROM students WHERE university
IN ('Stanford', 'MIT')
ORDER BY university;
```

<br>

- Which keyword is the correct one for custom columns?
  - 사용자 정의 column에 맞는 키워드는 무엇인가?

> `AS`

<br>

- What is the name of the aggregate function for calculating the sum?
  - 합계를 계산하는 총계 함수는 무엇인가?

> `SUM`

<br>

- Drag and drop from the options below to select name and age from "students", where age is greater than the average of all ages.
  - "students"에서 모든 age의 평균보다 큰 name과 age를 선택해라.

```mysql
SELECT name, age
FROM students
WHERE age > (SELECT AVG(age) FROM students);
```

<br>