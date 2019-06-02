---
layout: post
title: "(Filtering, Functions, Subqueries 03) IN, NOT IN 문"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

### The IN Operator

###### IN 연산자

<br>

- The `IN` operator is used when you want to compare a column with more than one value.
  - `IN` 연산자는 둘 이상의 값이 있는 column을 비교하려는 경우에 사용된다.

<br>

- For example, you might need to select all customers from New York, Los Angeles, and Chicago.
  - 예를 들어 New York, Los Angeles, Chicago의 모든 고객들을 선택하려고 한다.
- With the `OR` condition, your SQL would look like this:
  - `OR` 조건을 함께 사용하면 다음과 같다.

```mysql
SELECT * FROM customers
WHERE City = 'New York' OR City = 'Los Angeles' OR City = 'Chicago';
```

<br>

- Result:

![img](/assets/img/sql-sololearn-filtering & function & subquery-03-01.png)

<br>

<br>

- You can achieve the same result with a single `IN` condition, instead of the multiple `OR` conditions:
  - 여러 `OR` 조건 대신, 하나의 `IN` 조건으로 동일한 결과를 얻을 수 있다.

```mysql
SELECT * FROM customers
WHERE City IN ('New York', 'Los Angeles', 'Chicago');
```

<br>

- This would also produce the same result:
  - 위 코드는 동일한 결과를 출력한다.

![img](/assets/img/sql-sololearn-filtering & function & subquery-03-02.png)

<br>

> Note the use of `parentheses` in the syntax.
>
> 구문에서 `괄호`를 사용하는 것에 주의한다.

------

<br>

### The NOT IN Operator

###### NOT IN 연산자

<br>

- The `NOT IN` operator allows you to exclude a list of specific values from the result set.
  - `NOT IN` 연산자를 사용하면, result set에서 특정 값의 리스트를 제외할 수 있다.

<br>

- If we add the `NOT` keyword before `IN` in our previous query, customers living in those cities will be excluded:
  - 이전 query에서 `IN` 앞에 `NOT` 키워드를 추가하면, 해당 도시에 거주하는 고객들이 제외된다.

```mysql
SELECT * FROM customers
WHERE City NOT IN ('New York', 'Los Angeles', 'Chicago');
```

<br>

- Result:

![img](/assets/img/sql-sololearn-filtering & function & subquery-03-03.png)

------

<br>

### QUIZ

- Drag and drop from the options below to select users from NY and CA:
  - NY와 CA의 users를 선택해라.

```mysql
SELECT * FROM users
WHERE state = 'NY' OR state = 'CA';
```

<br>

- Select customers from NY, CA or NC, using the IN statement.
  - IN 문을 사용해서 NY, CA, NC의 고객을 선택해라.

```mysql
SELECT name, state FROM customers
WHERE state IN ('CA', 'NY', 'NC');
```

<br>

- Drag and drop from the options below to exclude customers from the states CA, NY.
  - CA, NY state의 고객들을 제외해라.

```mysql
SELECT name, state FROM customers
WHERE state NOT IN ('CA', 'NY');
```

<br>