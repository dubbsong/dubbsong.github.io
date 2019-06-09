---
layout: post
title: "(Challenges 02) QUIZ"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

### QUIZ

- Drag and drop from the options below to retrieve all students between the ages of 18 and 22.
  - 18세와 22세 사이의 모든 학생을 검색해라.

```mysql
SELECT name FROM students
WHERE age BETWEEN 18 AND 22;
```

<br>

- Drag and drop from the options below to update the "students" table to set Jake's university to MIT.
  - Jake의 대학을 MIT로 설정하기 위해 "students" 테이블을 업데이트해라.
- His id is 682.
  - Jake의 id는 682이다.

```mysql
UPDATE students SET university = 'MIT'
WHERE id = 682;
```

<br>

- When you inserted "elephant" as a new animal, you forgot to include the elephant's age.
  - "elephant"를 새로운 동물로 삽입했을 때, elephant의 나이를 잊어버렸다.
- Correct this mistake by updating the "zoo" table.
  - "zoo" 테이블을 업데이트해라.

```mysql
UPDATE zoo SET age = 14
WHERE animal = 'elephant';
```

<br>

- Drag and drop from the options below to update the food_balance to 23 for animals whose age is greater than the average age of the animals.
  - 나이가 동물의 평균 나이보다 큰 동물의 경우, food_balance를 23으로 업데이트해라.

```mysql
UPDATE zoo SET food_balance = 23
WHERE age > (SELECT AVG(age) FROM zoo);
```

<br>

- You need your customer's names, along with the names of the cities in which they live.
  - 고객이 사는 도시의 이름과 함께 고객의 이름이 필요하다.
- The names of the cities are stored in a separate table called "cities".
  - 도시의 이름은 "cities"라는 별도의 테이블에 저장되어 있다.

```mysql
SELECT customers.name, cities.name
FROM customers RIGHT OUTER JOIN cities
ON cities.id = customers.city_id;
```

<br>

- In the university's table containing student data, the students' last names have been omitted.
  - 학생 데이터가 있는 university의 테이블에서, 학생의 last_name이 생략되었다.
- Correct this by adding a new column to the table.
  - 테이블에 새 column을 추가해라.

```mysql
ALTER TABLE students
ADD last_name varchar(100);
```

<br>

- Drag and drop from the options below to retrieve from MIT, Stanford, and Harvard the names of all students whose first name is Jake.
  - MIT, Stanford, Harvard에서 Jake라는 이름을 가진 모든 학생의 이름을 검색해라.

```mysql
SELECT name FROM students
WHERE university
IN ('MIT', 'Stanford', 'Harvard') AND name = 'Jake';
```

<br>