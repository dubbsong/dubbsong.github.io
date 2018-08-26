---
layout: post
title: "Challenge 01"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

## QUIZ

- In the "users" table of website logins and passwords, select the first 10 records in the table.
  - 웹사이트 로그인과 비밀번호의 "users" 테이블에서 첫 번째 10개 레코드를 선택해라.

```mysql
SELECT * FROM users
LIMIT 10
```

<br>

- Drag and drop from the options below to create the table "users" to store website user logins and passwords.
  - 웹사이트 사용자 로그인과 비밀번호를 저장하기 위해 "users" 테이블을 생성해라.

```mysql
CREATE TABLE users(
id INT NOT NULL
AUTO_INCREMENT,
login VARCHAR(100),
password VARCHAR(100))
```

<br>

- Rearrange the query to select all students under age 21.
  - 21세 미만의 모든 학생을 선택해라.
- The result should be sorted according to the students' names.
  - 결과는 학생들의 이름에 따라 분류되어야 한다.

```mysql
SELECT *
FROM students
WHERE age < 21
ORDER BY name
```

<br>

- Your boss asks you to print the list of the first one hundred customers who have balances greater than $1000 or who are from NY.
  - boss가 $1000 이상의 잔고 또는 NY 출신 고객 100명을 출력하도록 요청한다.

```mysql
SELECT * FROM customers
WHERE balance > 1000
OR city = 'NY'
LIMIT 100
```

<br>

- You need the ages of all bears and lions.
  - 모든 곰과 사자의 나이가 필요하다.
- The first query shows the ages of bears and birds from zoo1, the other shows the ages of lions and crocodiles from zoo2.
  - 첫 번째 query는 동물원1의 곰과 새의 나이를 보여주고, 다른 하나는 동물원2의 사자와 악어의 나이를 보여준다.

```mysql
SELECT age FROM zoo1
WHERE animal IN ('bear', 'bird')
UNION
SELECT age FROM zoo2
WHERE animal IN ('lion', 'crocodile')
```

<br>

- Drag and drop from the options below to create a list of customers in the form "name is from city".
  - "name is from city" form으로 고객 목록을 생성해라.

```mysql
SELECT
CONCAT (name, 'is from', city)
FROM customers;
```

<br>

- The zoo administration wants a list of animals whose age is greater than the average age of all of the animals.
  - 동물원 관리자는 모든 동물의 평균 나이보다 큰 동물 목록을 원한다.

```mysql
SELECT * FROM zoo
WHERE age >
(SELECT AVG(age)
FROM zoo)
```

<br>

- There are many wolves in the zoo: black wolf, white wolf, lucky wolf, little wolf.
  - 동물원에 검은 늑대, 하얀 늑대, 운이 좋은 늑대, 작은 늑대 등 많은 늑대가 있다.
- They all have 'wolf' at the end of their names.
  - 그들 모두는 그들 이름의 끝에 'wolf'를 가지고 있다.
- Print the ages of all of the wolves.
  - 모든 늑대의 나이를 출력해라.

```mysql
SELECT age FROM zoo
WHERE animal LIKE '%wolf'
```

<br>