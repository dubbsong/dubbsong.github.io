---
layout: post
title: "(Filtering, Functions, Subqueries 08) QUIZ"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

### QUIZ

- Fill in the blanks to select all values from the "students" table in which the field "university" equals "MIT".
  - "students" 테이블의 "university" 필드가 MIT인 모든 값을 선택해라.

```mysql
SELECT * FROM students WHERE university = 'MIT';
```

<br>

- Rearrange the code to select students from MIT and Stanford, and order the results by the "university" column.
  - MIT와 Stanford의 학생을 선택해라.
  - "university" column으로 결과를 정렬해라.

```mysql
SELECT name, university FROM students
WHERE university IN('Stanford', 'MIT')
ORDER BY university;
```

<br>

- Which keyword is the correct one for custom columns?
  - 사용자 정의 column에 대한 키워드는 무엇인가?

> `AS`

<br>

- What is the name of the aggregate function for calculating the sum?
  - 합을 계산하는 데 사용되는 합계 함수의 이름은 무엇인가?

> `SUM`

<br>

- Drag and drop from the options below to select name and age from "students", where age is greater than the average of all ages.
  - "students" 테이블에서 모든 나이의 평균보다 큰 나이의 name과 age를 선택해라.
- Use a subquery to calculate the average value of age.
  - subquery를 사용해서 나이의 평균 값을 계산해라.

```mysql
SELECT name, age FROM students
WHERE age > (SELECT AVG(age) FROM students);
```

<br>