---
layout: post
title: "(Filtering, Functions, Subqueries 07) LIKE & MIN 키워드"
categories: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

## The LIKE Operator

###### LIKE 연산자

<br>

- The `LIKE` keyword is useful when specifying a `search condition` within your WHERE clause.
  - `LIKE` 키워드는 WHERE 절에서 `검색 조건`을 지정할 때 유용하다.

```mysql
SELECT column_name(s)
FROM table_name
WHERE column_name LIKE pattern;
```

<br>

- SQL `pattern` matching enables you to use "_" to match any single character and "%" to match an arbitrary number of characters (including zero characters).
  - SQL `pattern` 일치는 "_"를 사용해서 하나의 문자를 일치시킨다.
  - 그리고 "%"를 사용해서 임의의 숫자 문자(0 문자 포함)를 일치시킨다.

<br>

- For example, to select employees whose *FirstNames* begin with the letter `A`, you would use the following query:
  - 예를 들어 *FirstNames*가 `A` 문자로 시작하는 employee를 선택하려면, 다음 query를 사용해야 한다.

```mysql
SELECT * FROM employees
WHERE FirstName LIKE 'A%';
```

<br>

- Result:

![img](/assets/img/sql-sololearn-filtering&functions&subqueries-07-01.png)

<br>

- As another example, the following SQL query selects all employees with a *LastName* ending with the letter "s":
  - 다른 예로, 다음 SQL query는 문자 "s"로 끝나는 *LastName*을 가진 모든 employee를 선택한다.

```mysql
SELECT * FROM employees
WHERE LastName LIKE '%s';
```

<br>

- Result:

![img](/assets/img/sql-sololearn-filtering&functions&subqueries-07-02.png)

<br>

> The % wildcard can be used `multiple` times within the same pattern.
>
> % wildcard는 동일한 pattern 내에서 `여러 번` 사용할 수 있다.

------

<br>

## The MIN Function

###### MIN 함수

<br>

- The `MIN` function is used to return the minimum value of an expression in a SELECT statement.
  - `MIN` 함수는 SELECT 문에서 표현식의 최소값을 반환하는 데 사용된다.

<br>

- For example, you might wish to know the minimum salary among the employees.
  - 예를 들어, employee 간의 최저 salary를 알고 싶을 수 있다.

```mysql
SELECT MIN(Salary) AS Salary FROM employees;
```

<br>

![img](/assets/img/sql-sololearn-filtering&functions&subqueries-07-03.png)

<br>

> All of the SQL functions can be combined together to create a single expression.
>
> 모든 SQL 함수를 결합해서 하나의 표현식을 작성할 수 있다.

------

<br>

## QUIZ

- Drag and drop from the options below to search "boxes" in the "name" column of the "items" table.
  - "items" 테이블의 "name" column에서 "boxes"를 검색해라.

```mysql
SELECT seller_id FROM items
WHERE name LIKE '%boxes';
```

<br>

- Drag and drop from the options below to complete the statement, which selects "name" and minimum of the "cost" from "items", filtering by name and seller id.
  - name과 seller id별로 필터링해서, "name"과 "items"의 최저 "cost"를 선택하는 명령문을 완성해라.

```mysql
SELECT name, MIN(cost)
FROM items WHERE name
LIKE '%boxes of frogs'
AND seller_id IN (68, 6, 18);
```

<br>