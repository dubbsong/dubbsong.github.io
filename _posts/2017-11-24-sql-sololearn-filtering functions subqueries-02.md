---
layout: post
title: "02. AND, OR로 필터링하기 (Filtering, Functions, Subqueries)"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com) SQL 번역

<br>

# Filtering with AND, OR

###### AND, OR로 필터링하기

------

<br>

<br>

## Logical Operators

###### 논리 연산자

<br>

- Logical operators can be used to combine two Boolean values and return a result of `true`, `false`, or `null`.
  - 논리 연산자를 사용해서 두 개의 Boolean 값을 조합할 수 있다.
  - 그리고 `true`, `false` 또는 `null`의 결과를 반환할 수 있다.
- The following operators can be used:
  - 다음 연산자를 사용할 수 있다.

![sololearn img](/assets/img/sololearn-sql-filtering functions subqueries-02-01.png)

<br>

- When retrieving data using a `SELECT` statement, use logical operators in the `WHERE` clause to combine multiple conditions.
  - `SELECT` 문을 사용해서 데이터를 검색할 때, `WHERE` 절에 논리 연산자를 사용해서 여러 조건을 조합해라.

<br>

- If you want to select rows that satisfy all of the given conditions, use the logical operator, `AND`.
  - 주어진 조건을 모두 만족하는 row를 선택하려면, 논리 연산자 `AND`를 사용해라.

![sololearn img](/assets/img/sololearn-sql-filtering functions subqueries-02-02.png)

<br>

- To find the names of the customers between 30 to 40 years of age, set up the query as seen here:
  - 30 - 40세 사이의 고객 이름을 찾으려면, 다음과 같이 query를 설정해라.

```mysql
SELECT ID, FirstName, LastName, Age
FROM customers
WHERE Age >= 30 AND Age <= 40;
```

<br>

- This results in the following output:
  - 결과는 다음과 같다.

![sololearn img](/assets/img/sololearn-sql-filtering functions subqueries-02-03.png)

<br>

> You can combine as many conditions as needed to return the desired results.
>
> 원하는 결과를 반환하는 데 필요한 조건을 조합할 수 있다.

------

<br>

## OR

- If you want to select rows that satisfy at least one of the given conditions, you can use the logical `OR` operator.
  - 주어진 조건 중 하나를 만족하는 row를 선택하려면, 논리 연산자 `OR`를 사용할 수 있다.

<br>

- The following table describes how the logical `OR` operator functions:
  - 다음 테이블에서는 논리 연산자 `OR`의 기능에 대해 설명한다.

![sololearn img](/assets/img/sololearn-sql-filtering functions subqueries-02-04.png)

<br>

- For example, if you want to find the customers who live either in New York or Chicago, the query would look like this:
  - 예를 들어, New York이나 Chicago에 살고 있는 고객을 찾으려면 query는 다음과 같다.

```mysql
SELECT * FROM customers
WHERE City = 'New York' OR City = 'Chicago';
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-sql-filtering functions subqueries-02-05.png)

------

<br>

## Combining AND & OR

###### AND와 OR 조합

<br>

- The SQL `AND` and `OR` conditions may be combined to test multiple conditions in a query.
  - SQL `AND`와 `OR` 조건을 조합해서 query의 여러 조건을 테스트할 수 있다.
- These two operators are called `conjunctive operators`.
  - 이 두 연산자를 `결합 연산자`라고 한다.

<br>

- When combining these conditions, it is important to use `parentheses`, so that the order to evaluate each condition is known.
  - 이러한 조건을 조합할 때, 각 조건을 평가하는 순서를 알 수 있도록 `괄호`를 사용하는 것이 중요하다.

<br>

- Consider the following table:
  - 다음 테이블을 고려해라.

![sololearn img](/assets/img/sololearn-sql-filtering functions subqueries-02-06.png)

<br>

- The statement below selects all customers from the city "New York" `AND` with the age equal to "30" `OR` "35":
  - 아래의 명령문은 "New York" city에서 "30" `OR` "35"와 동등한 나이의 모든 고객을 선택한다.

```mysql
SELECT * FROM customers
WHERE City = 'New York'
AND (Age=30 OR Age=35);
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-sql-filtering functions subqueries-02-07.png)

<br>

> You can nest as many conditions as you need.
>
> 필요한 만큼 조건을 중첩할 수 있다.

------

<br>

## QUIZ

- Drag and drop from the options below to select customers who live in Hollywood, CA.
  - Hollywood, CA에 사는 고객을 선택해라.

```mysql
SELECT * FROM customers
WHERE state = 'CA'
AND city = 'Hollywood'
```

<br>

- Drag and drop from the options below to select customers who live either in CA or in Boston.
  - CA 또는 Boston에 거주하는 고객을 선택해라.

```mysql
SELECT name, state, city
FROM customers
WHERE state = 'CA'
OR city = 'Boston';
```

<br>

- Drag and drop from the options below to select customers whose ids are either 1 or 2, and whose city is "Boston".
  - ID가 1 또는 2이고, city가 "Boston"인 고객을 선택해라.

```mysql
SELECT * FROM customers
WHERE (id = 1 OR id = 2)
AND city = 'Boston'
```

<br>