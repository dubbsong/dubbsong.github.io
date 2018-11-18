---
layout: post
title: "(Filtering, Functions, Subqueries 01) WHERE 문"
categories: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

## The WHERE Statement

###### WHERE 문

<br>

- The `WHERE` clause is used to extract only those records that fulfill a specified criterion.
  - `WHERE` 절은 지정된 기준을 충족하는 record만 추출하는 데 사용된다.

<br>

- The syntax for the WHERE clause:
  - WHERE 절의 구문은 다음과 같다.

```mysql
SELECT column_list
FROM table_name
WHERE condition;
```

<br>

- Consider the following table:
  - 다음 테이블을 살펴보자.

![img](/assets/img/sql-sololearn-filtering&functions&subqueries-01-01.png)

<br>

- In the above table, to SELECT a specific record:
  - 위의 테이블에서 특정 record를 선택하는 것은 다음과 같다.

```mysql
SELECT * FROM customers
WHERE ID = 7;
```

<br>

![img](/assets/img/sql-sololearn-filtering&functions&subqueries-01-02.png)

<br>

> The WHERE clause is used to extract only those records that fulfill a specified criterion.
>
> WHERE 절은 지정된 기준을 충족하는 record만 추출하는 데 사용된다.

------

<br>

## SQL Operators

###### SQL 연산자

<br>

- `Comparison Operators` and `Logical Operators` are used in the WHERE clause to filter the data to be selected.
  - WHERE 절에서 `비교 연산자`와 `논리 연산자`를 사용해 선택할 데이터를 필터링한다.

<br>

- The following comparison operators can be used in the WHERE clause:
  - 다음 비교 연산자를 WHERE 절에서 사용될 수 있다.

![img](/assets/img/sql-sololearn-filtering&functions&subqueries-01-03.png)

<br>

- For example, we can display all customers names listed in our table, with the exception of the one with ID 5.
  - 예를 들어 ID가 5인 customer의 이름을 제외하고, 테이블에 나열된 customer의 이름을 표시할 수 있다.

```mysql
SELECT * FROM customers
WHERE ID != 5;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-filtering&functions&subqueries-01-04.png)

<br>

> As you can see, the record with ID=5 is excluded from the list.
>
> 보다시피, ID가 5인 record는 list에서 제외된다.

------

<br>

## The BETWEEN Operator

###### BETWEEN 연산자

<br>

- The BETWEEN operator selects values within a range.
  - BETWEEN 연산자는 범위 내의 값을 선택한다.
- The first value must be lower bound and the second value, the upper bound.
  - 첫 번째 값은 하한(lower bound)이어야 하고, 두 번째 값은 상한(upper bound)이어야 한다.

<br>

- The syntax for the BETWEEN clause is as follows:
  - BETWEEN 절의 구문은 다음과 같다.

```mysql
SELECT column_name(s)
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
```

<br>

- The following SQL statement selects all records with IDs that fall between 3 and 7:
  - 다음 SQL 문은 ID가 3에서 7 사이인 모든 record를 선택한다.

```mysql
SELECT * FROM customers
WHERE ID BETWEEN 3 AND 7;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-filtering&functions&subqueries-01-05.png)

<br>

> As you can see, the lower bound and upper bound are both included in the range.
>
> 보다시피, 하한과 상한은 모두 범위에 포함된다.

------

<br>

## Text Values

###### 텍스트 값

<br>

- When working with text columns, surround any text that appears in the statement with `single quotation marks(')`.
  - 텍스트 column을 사용해서 작업할 때는, 명령문에 나타나는 모든 텍스트를 `작은 따옴표(')`로 묶는다.

<br>

- The following SQL statement selects all records in which the *City* is equal to 'New York'.
  - 다음 SQL 문은 *City*가 'New York'과 같은 모든 record를 선택한다.

```mysql
SELECT ID, FirstName, LastName, City
FROM customers
WHERE City = 'New York';
```

<br>

![img](/assets/img/sql-sololearn-filtering&functions&subqueries-01-06.png)

<br>

> If your text contains an apostrophe (single quote), you should use two single quote characters to escape the apostrophe.
>
> 텍스트에 아포스트로피(작은 따옴표)가 포함되어 있다면, 두 개의 작은 따옴표 문자를 사용해서 아포스트로피를 이스케이프 해야 한다.

> 예: `'Can''t'`

------

<br>

## QUIZ

- Drag and drop from the options below to select the name of the student whose id is equal to 23.
  - id가 23인 학생의 이름을 선택해라.

```mysql
SELECT id, name
FROM students
WHERE id=23;
```

<br>

- Fill in the blank to select student names whose id is greater than or equal to 12.
  - id가 12보다 크거나 같은 student 이름을 선택해라.

```mysql
SELECT id, name
FROM students WHERE id >= 12;
```

<br>

- Drag and drop from the options below to build a query to select the names of students whose ids are between 13 and 45.
  - id가 13에서 45 사이인 student의 이름을 선택하는 query를 작성해라.

```mysql
SELECT id, name
FROM students
WHERE id
BETWEEN 13 AND 45;
```

<br>

- Rearrange the code to select all values from the "people" table where the city equalts to "Boston".
  - "people" 테이블에서 city가 "Boston"인 모든 값을 선택해라.

```mysql
SELECT * FROM people
WHERE city='Boston';
```

<br>