---
layout: post
title: "(Filtering, Functions, Subqueries 07) LIKE 연산자 & MIN 함수"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

### The LIKE Operator

###### LIKE 연산자

<br>

- The `LIKE` keyword is useful when specifying a `search condition` within your WHERE clause.
  - `LIKE` 키워드는 WHERE 절에서 `검색 조건`을 지정할 때 유용하다.

```sql
SELECT column_name(s) FROM table_name
WHERE column_name LIKE pattern;
```

<br>

- SQL `pattern` matching enables you to use "_" to match any single character and "%" to match an arbitrary number of characters (including zero characters).
  - SQL `pattern` 일치는 "_"를 사용해 하나의 문자와 일치시키고, "%"를 사용해 임의의 문자 수(0 문자 포함)를 일치시킬 수 있다.

<br>

- For example, to select employees whose *FirstNames* begin with the letter `A`, you would use the following query:
  - 예를 들어, *FirstName*이 `A`로 시작하는 직원을 선택하기 위한 query는 다음과 같다.

```mysql
SELECT * FROM employees
WHERE FirstName LIKE 'A%';
```

<br>

- Result:

![img](/assets/img/sql-sololearn-filtering & function & subquery-07-01.png)

<br>

- As another example, the following SQL query selects all employees with a *LastName* ending with the letter "s":
  - 또 다른 예로, 다음 SQL query는 *LastName*이 문자 "s"로 끝나는 모든 직원을 선택한다.

```mysql
SELECT * FROM employees
WHERE LastName LIKE '%s';
```

<br>

- Result:

![img](/assets/img/sql-sololearn-filtering & function & subquery-07-02.png)

<br>

> The % wildcard can be used `multiple` times within the same pattern.
>
> % 와일드카드(임의 문자 기호)는 동일한 pattern 내에서 `여러` 번 사용할 수 있다.

------

<br>

### The MIN Function

###### MIN 함수

<br>

- The `MIN` function is used to return the minimum value of an expression in a SELECT statement.
  - SELECT 문에서 `MIN` 함수는, 표현식의 최소값을 반환하는 데 사용된다.

<br>

- For example, you might wish to know the minimum salary among the employees.
  - 예를 들어, 직원 간의 최소 급여를 알아보자.

```mysql
SELECT MIN(Salary) As Salary FROM employees;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-filtering & function & subquery-07-03.png)

<br>

> All of the SQL functions can be combined together to create a single expression.
>
> 모든 SQL 함수를 결합해서 하나의 표현식으로 작성할 수 있다.

------

<br>

### QUIZ

- Drag and drop from the options below to search "boxes" in the "name" column of the "items" table.
  - "items" 테이블의 "name" column에서 "boxes"를 검색해라.

```mysql
SELECT seller_id FROM items
WHERE name LIKE '%boxes';
```

<br>

- Drag and drop from the options below to complete the statement, which selects "name" and minimum of the "cost" from "items", filtering by name and seller id.
  - "name"과 "items"의 최소 "cost"를 선택하는 명령문을 작성해라.
  - name과 seller_id로 필터링한다.

```mysql
SELECT name, MIN(cost) FROM items
WHERE name LIKE '%boxes of frogs' AND seller_id IN (68, 6, 18);
```

<br>