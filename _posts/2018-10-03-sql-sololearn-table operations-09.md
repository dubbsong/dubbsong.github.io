---
layout: post
title: "(JOIN, Table Operations 09) VIEW"
categories: dev
tags: db
---

###### [SoloLearn](https://www.sololearn.com/) SQL 번역

<br>

### Views

###### View

<br>

- In SQL, a VIEW is a `virtual table` that is based on the result-set of an SQL statement.
  - SQL에서 VIEW는 SQL 문의 result-set을 기반으로 하는 `가상 테이블`이다.

<br>

- A view contains rows and columns, just like a real table.
  - 실제 테이블과 마찬가지로, view에는 row와 column이 포함된다.

- Views allows us to:
  - view를 사용하면 다음을 수행할 수 있다.

<br>

1. Structure data in a way that users or classes of users find natural or intuitive.
   - 사용자 또는 사용자 class가 자연스럽고 직관적인 방식으로 데이터를 구조화한다.
2. Restrict access to the data in such a way that a user can see and (sometimes) modify exactly what they need and no more.
   - 사용자가 볼 수 있고, 사용자가 정확히 필요한 것을 수정할 수 있는 방식으로 데이터에 대한 액세스를 제한한다.
3. Summarize data from various tables and use it to generate reports.
   - 여러 테이블의 데이터를 요약하고, 이를 사용해서 report를 생성한다.

<br>

- To create a view:
  - view를 생성하기 위한 구문은 다음과 같다.

```sql
CREATE VIEW view_name AS
SELECT column_name(s)
FROM table_name
WHERE condition;
```

<br>

> The SELECT query can be as complex as you need it to be.
>
> SELECT query는 필요한 만큼 복잡해질 수 있다.

> It can contain multiple JOINS and other commands.
>
> 여러 JOINS와 다른 명령들을 포함할 수 있다.

------

<br>

### Creating Views

###### view 생성하기

<br>

- Consider the `Employees` table, which contains the following records:
  - 다음 레코드가 포함된 `Employees` 테이블을 살펴보자.

![img](/assets/img/sql-sololearn-table operations-09-01.png)

<br>

- Let's create a view that displays each employee's FirstName and Salary.
  - 각 직원의 FirstName과 Salary를 보여주는 view를 생성해보자.

```mysql
CREATE VIEW List AS
SELECT FirstName, Salary FROM Employees;
```

<br>

- Now, you can query the `List` view as you would query an actual table.
  - 이제 실제 테이블의 query를 작성하는 것처럼, `List` view의 query를 작성할 수 있다.

```mysql
SELECT * FROM List;
```

<br>

- This would produce the following result:
  - 위의 코드는 다음 결과를 출력한다.

![img](/assets/img/sql-sololearn-table operations-09-02.png)

<br>

> A view always shows up-to-date data.
>
> view는 항상 최신 데이터를 보여준다.

> The database engine uses the view's SQL statement to recreate the data each time a user queries a view.
>
> 데이터베이스 엔진은 사용자가 view를 query할 때마다 view의 SQL 문을 사용해서 데이터를 다시 작성한다.

------

<br>

### Updating a View

###### view 업데이트하기

<br>

- You can update a view by using the following syntax:
  - 다음 구문을 사용해서 view를 업데이트할 수 있다.

```sql
CREATE OR REPLACE VIEW view_name AS
SELECT column_name(s)
FROM table_name
WHERE condition;
```

<br>

- The example below updates our `List` view to select also the LastName:
  - 아래 예제는 `List` view를 업데이트해서 LastName도 선택한다.

```mysql
CREATE OR REPLACE VIEW List AS
SELECT FirstName, LastName, Salary FROM Employees;
```

<br>

- Result:

![img](/assets/img/sql-sololearn-table operations-09-03.png)

<br>

- You can delete a view with the DROP VIEW command.
  - DROP VIEW 명령으로 view를 삭제할 수 있다.

```mysql
DROP VIEW List;
```

<br>

> It is sometimes easier to drop a table and recreate it instead of using the ALTER TABLE statement to change the table's definition.
>
> ALTER TABLE 문을 사용해서 테이블의 정의를 변경하는 대신, 가끔은 테이블을 삭제하고 다시 생성하는 게 더 쉽다.

------

<br>

### QUIZ

- Which command is used to create a view?
  - view를 생성하는 데 사용되는 명령어는 무엇인가?

> `CREATE VIEW`

<br>

- Drag and drop from the options below to create a view named "temp" for students with the highest marks.
  - 가장 높은 점수를 가진 학생에 대한 "temp"라는 view를 생성해라.

```mysql
CREATE VIEW temp AS
SELECT id, name, mark FROM students
ORDER BY mark DESC LIMIT 10;
```

<br>

- Which statement in regard to views is correct?
  - 다음 중 view에 관해 올바른 설명은 무엇인가?

> [ ] Views must be updated manually
>
> [ ] Views need space in the database to be stored
>
> [x] `Views are being updated dynamically`

<br>