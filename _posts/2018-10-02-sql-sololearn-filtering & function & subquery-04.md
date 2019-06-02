---
layout: post
title: "(Filtering, Functions, Subqueries 04) 사용자 정의 column"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

### The CONCAT Function

###### CONCAT 함수

<br>

- The `CONCAT` function is used to concatenate two or more text values and returns the concatenating string.
  - `CONCAT` 함수는 두 개 이상의 텍스트 값을 연결하는 데 사용되고, 연결 문자열을 반환한다.

<br>

- Let's concatenate the *FirstName* with the *City*, separating them with a *comma*:
  - *FirstName*과 *City*를 *쉼표*로 구분해서 연결해보자.

```mysql
SELECT CONCAT(FirstName, ',', City) FROM customers;
```

<br>

- The output result is:
  - 출력 결과는 다음과 같다.

![img](/assets/img/sql-sololearn-filtering & function & subquery-04-01.png)

<br>

> The CONCAT() function takes two or more parameters.
>
> CONCAT() 함수는 두 개 이상의 매개변수를 사용한다.

------

<br>

### The AS Keyword

###### AS 키워드

<br>

- A concatenation results in a new column.
  - 연결은 새로운 column을 출력한다.
- The default column name will be the CONCAT function.
  - column 이름의 기본 값은 CONCAT 함수가 된다.
- You can assign a custom name to the resulting column using the `AS` keyword:
  - `AS` 키워드를 사용해서, 결과 column에 사용자 정의 이름을 지정할 수 있다.

```mysql
SELECT CONCAT(FirstName, ',', City) AS new_column FROM customers;
```

<br>

- And when you run the query, the column name appears to be changed.
  - query를 실행하면, column 이름이 변경된 것을 확인할 수 있다.

![img](/assets/img/sql-sololearn-filtering & function & subquery-04-02.png)

------

<br>

### Arithmetic Operators

###### 산술 연산자

<br>

- Arithmetic operators perform arithmetical operations on numeric operands.
  - 산술 연산자는 피연산자 수에 대해 산술 연산을 수행한다.
- The Arithmetic operators include addition (\+), subtraction (\-), multiplication (\*) and division (/).
  - 산술 연산자에는 더하기(\+), 빼기(\-), 곱하기(\*), 나누기(/)가 포함된다.

<br>

- The following `employees` table shows employee names and salaries:
  - 다음 `employees` 테이블은 직원의 이름과 급여를 보여준다.

![img](/assets/img/sql-sololearn-filtering & function & subquery-04-03.png)

<br>

- The example below adds 500 to each employee's salary and selects the result:
  - 아래 예제는 각 직원의 급여에 500을 추가하고, 결과를 선택한다.

```mysql
SELECT ID, FirstName, LastName, Salary+500 AS Salary FROM employees;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-filtering & function & subquery-04-04.png)

<br>

> Parentheses can be used to force an operation to take priority over any other operators.
>
> 괄호는 다른 연산자보다 연산을 강제 우선하는 데 사용된다.

> They are also used to improve code readability.
>
> 코드 가독성을 높이는 데에도 사용된다.

------

<br>

### QUIZ

- What do we call the function used for concatenation?
  - 연결에 사용되는 함수는 무엇인가?

> `CONCAT`

<br>

- Type in the keyword used to create custom columns.
  - 사용자 정의 column을 생성하는 데 사용되는 키워드는 무엇인가?

> `AS`

<br>

- Drag and drop from the options below to select concatenated "city" and "state" columns, represented with a new custom column named "new_address".
  - 연결된 "city"와 "state" column을 선택해라.
  - "new_address"라는 새로운 사용자 column 이름으로 나타낸다.

```mysql
SELECT CONCAT (city, ',', state) AS new_address FROM customers;
```

<br>