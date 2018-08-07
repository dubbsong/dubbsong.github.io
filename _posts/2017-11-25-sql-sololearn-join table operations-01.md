---
layout: post
title: "01. 테이블 결합하기 (JOIN, Table Operations)"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com) SQL 번역

<br>

# Joining Tables

###### 테이블 결합하기

<br>

- All of the queries shown up until now have selected from just one table at a time.
  - 지금까지 표시된 모든 query는 한 번에 하나의 테이블에서만 선택되었다.

<br>

- One of the most beneficial features of SQL is the ability to combine data from two or more tables.
  - SQL의 가장 유익한 기능 중 하나는, 두 개 이상의 테이블에서 데이터를 결합하는 기능이다.

<br>

- In the two tables that follow, the table named `customers` stores information about customers:
  - 다음 두 테이블에서 `customers`라는 테이블은 고객에 대한 정보를 저장한다.

![sololearn img](/assets/img/sololearn-sql-join table operations-01-01.png)

<br>

- The `orders` table stores information about individual orders with their corresponding amount:
  - `orders` 테이블은 개별 순서에 대한 정보를 해당 금액과 함께 저장한다.

![sololearn img](/assets/img/sololearn-sql-join table operations-01-02.png)

<br>

> In SQL, `"joining tables"` means combining data from two or more tables.
>
> SQL에서 `"joining tables"`는 두 개 이상의 테이블에서 데이터를 결합하는 것을 의미한다.

> A table join creates a `temporary table` showing the data from the joined tables.
>
> table join은 joined 테이블의 데이터를 보여주는 `임시 테이블`을 생성한다.

<br>

<br>

- Rather than storing the customer name in both tables, the `orders` table contains a reference to the `customer ID` that appears in the customers table.
  - 두 테이블 모두에 고객 이름을 저장하는 대신, `orders` 테이블에는 고객 테이블에 나타나는 `customer ID`에 대한 참조가 포함된다.
- This approach is more efficient, as opposed to storing the same text values in both tables.
  - 두 테이블 모두에 동일한 텍스트 값을 저장하는 것과는 대조적으로, 이 접근법이 더 효율적이다.
- In order to be able to select the corresponding data from both tables, we will need to `join` them on that condition.
  - 두 테이블에서 해당 데이터를 선택할 수 있으려면, 해당 조건에서 `결합` 해야 한다.

<br>

<br>

- To join the two tables, specify them as a comma-separated list in the FROM clause:
  - 두 테이블을 결합하려면, 쉼표로 FROM 절에서 구분된 목록으로 지정해라.

```mysql
SELECT customers.ID, customers.Name, orders.Name, orders.Amount
FROM customers, orders
WHERE customers.ID=orders.Customer_ID
ORDER BY customers.ID;
```

<br>

> Each table contains "ID" and "Name" columns, so in order to select the correct ID and Name, `fully qualified names` are used.
>
> 각 테이블에는 "ID"와 "Name" column이 있으므로, 정확한 ID와 이름을 선택하려면, `fully qualified names`이 사용된다.

<br>

- Note that the `WHERE` clause "joins" the tables on the condition that the `ID` from the `customers` table should be equal to the `customer_ID` of the `orders` table.
  - `WHERE` 절은 `customers` 테이블의 `ID`가 `orders` 테이블의 `customer_ID`와 같아야 한다는 조건에서 테이블을 "결합" 한다.

<br>

- Result:

![sololearn img](/assets/img/sololearn-sql-join table operations-01-03.png)

<br>

- The returned data shows customer orders and their corresponding amount.
  - 반환된 데이터는 고객의 순서와 해당 금액을 보여준다.

<br>

> Specify multiple table names in the FROM by comma-separating them.
>
> 여러 테이블 이름을 쉼표로 구분해서 FROM에 지정해라.

------

<br>

## QUIZ

- What does the Table Join do?
  - Table Join은 무엇을 하는가?

> `Creates a temporary table with the joined tables' data`

<br>

- Drag and drop from the options below to select "id" from "students".
  - "students"에서 "id"를 선택해라.
- Order the results by id, in descending order.
  - 결과를 ID 별로 내림차순으로 정렬해라.

```mysql
SELECT id FROM students
ORDER BY id DESC
```

<br>

- Drag and drop from the options below to complete the following statement, which shows item names and the names of customers who bought the items.
  - 항목 이름과 항목을 구입한 고객의 이름을 표시하는 명령문을 완성해라.

```mysql
SELECT customers.name, items.names
FROM customers, items
WHERE items.seller_id = customers.id
```

<br>
