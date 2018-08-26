---
layout: post
title: "Challenge 02"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

## QUIZ

- Drag and drop from the options below to retrieve all students between the ages of 18 and 22.
  - 18세에서 22세 사이의 모든 학생의 나이를 검색해라.

```mysql
SELECT name FROM students
WHERE age
BETWEEN 18 AND 22;
```

<br>

- Drag and drop from the options below to update the "students" table to set Jake's university to MIT.
  - Jake의 대학을 MIT에 맞추기 위해 "students" 테이블을 업데이트해라.
- His id is 682.
  - Jake의 id는 682이다.

```mysql
UPDATE students
SET university='MIT'
WHERE id=682
```

<br>

- When you inserted "elephant" as a new animal, you forgot to include the elephant's age.
  - 새 동물로 "elephant"를 삽입할 때, elephant의 나이 포함을 잊어버렸다.
- Correct this mistake by updating the "zoo" table.
  - "zoo" 테이블을 업데이트해서 이 실수를 해결해라.

```mysql
UPDATE zoo
SET age=14
WHERE animal='elephant'
```

<br>

- Drag and drop from the options below to update the food_balance to 23 for animals whose age is greater than the average age of the animals.
  - 동물의 평균 나이보다 큰 동물의 경우, food_balance를 23으로 업데이트해라.

```mysql
UPDATE zoo
SET food_balance=23
WHERE age >
(SELECT AVG(age)
FROM zoo);
```

<br>

- You need your customer's names, along with the names of the cities in which they live.
  - 고객이 사는 cities의 이름과 함께 customer의 이름이 필요하다.
- The names of the cities are stored in a separate table called "cities".
  - 도시의 이름은 "cities"라는 별도의 테이블에 저장된다.

```mysql
SELECT customers.name, cities.name
FROM customers
RIGHT
OUTER JOIN cities
ON cities.id=customers.city_id;
```

<br>

- In the university's table containing student data, the students' last names have been omitted.
  - 학생 데이터가 포함된 university의 테이블에서, students의 last name이 생략되었다.

- Correct this by adding a new column to the table.
  - 테이블에 새 column을 추가해서 이를 해결해라.

```mysql
ALTER TABLE students
ADD last_name VARCHAR(100);
```

<br>

- Drag and drop from the options below to retrieve from MIT, Stanford, and Harvard the names of all students whose first name is Jake.
  - MIT, Stanford, Harvard에서 Jake라는 first name을 가진 모든 학생들의 이름을 검색해라.

```mysql
SELECT name FROM students
WHERE university
IN ('MIT', 'Stanford', 'Harvard')
AND name='Jake';
```

<br>