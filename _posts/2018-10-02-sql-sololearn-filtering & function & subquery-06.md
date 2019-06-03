---
layout: post
title: "(Filtering, Functions, Subqueries 06) Subquery (서브쿼리)"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

### Subquery

###### Subquery (서브쿼리)

<br>

- A `subquery` is a query within another query.
  - `subquery(서브쿼리)`는 다른 query 내의 query이다.

<br>

- Let's consider an example.
  - 예제를 살펴보자.
- We might need the list of all employees whose salaries are greater than the average.
  - 급여가 평균보다 큰 모든 직원의 리스트가 필요할 수 있다.
- First, calculate the average:
  - 먼저, 평균을 계산한다.

```mysql
SELECT AVG(Salary) FROM employees;
```

<br>

- As we already know the average, we can use a simple WHERE to list the salaries that are `greater` than that number.
  - 이미 평균을 알고 있으므로, WHERE를 사용해서 평균보다 `큰` 급여를 나열할 수 있다.

```mysql
SELECT FirstName, Salary FROM employees
WHERE Salary > 3100
ORDER BY Salary DESC;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-filtering & function & subquery-06-01.png)

<br>

> The `DESC` keyword sorts results in `descending order`.
>
> `DESC` 키워드는 결과를 `내림차순`으로 정렬한다.

> Similarly, `ASC` sorts the results in `ascending order`.
>
> 마찬가지로, `ASC` 키워드는 결과를 `오름차순`으로 정렬한다.

<br>

<br>

- A single subquery will return the same result more easily.
  - subquery는 동일한 결과를 더 쉽게 반환한다.

```mysql
SELECT FirstName, Salary FROM employees
WHERE Salary > (SELECT AVG(Salary) FROM employees)
ORDER BY Salary DESC;
```

<br>

- The same result will be produced.
  - 동일한 결과가 출력된다.

![img](/assets/img/sql-sololearn-filtering & function & subquery-06-02.png)

<br>

> Enclose the subquery in `parentheses`.
>
> subquery는 `괄호`로 둘러싼다.

> Also, note that there is no semicolon at the end of the subquery, as it is part of our single query.
>
> subquery 끝에 세미콜론이 없다는 것에 주의한다.

------

<br>

### QUIZ

- Drag and drop from the options below to select all items from the "items" table for which cost is greater than 463.
  - "items" 테이블에서 cost가 463보다 큰 모든 item을 선택해라.
- Order the result by cost in descending order.
  - cost는 내림차순으로 정렬한다.

```mysql
SELECT * FROM items
WHERE cost > 463
ORDER BY cost DESC;
```

<br>

- Drag and drop from the options below to select all items from the "items" table for which the cost is greater than the average of costs.
  - "items" 테이블에서 cost의 평균보다 큰 모든 item을 선택해라.
- Use a subquery to calculate the average cost.
  - subquery를 사용해서 평균 cost를 계산한다.

```mysql
SELECT * FROM items
WHERE cost > (SELECT AVG(cost) FROM items);
```

<br>