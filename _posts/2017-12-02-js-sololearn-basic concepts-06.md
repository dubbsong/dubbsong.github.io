---
layout: post
title: "SoloLearn 번역 - 06. Logical or Boolean Operators (Basic Concepts)"
categories: javascript
tags: JS
---

## Logical Operators (논리 연산자)

- **Logical** Operators, also known as **Boolean** Operators, evaluate the expression and return **true** or **false**.
  - **불리언** 연산자라고도 하는 **논리** 연산자는 표현식을 평가하고 **true** 또는 **false**를 반환한다.

<br>

- The table below explains the logical operators (**AND**, **OR**, **NOT**).
  - 아래 테이블은 논리 연산자(**AND**, **OR**, **NOT**)를 설명한다.

![SoloLearn img](/assets/img/sololearn-js-basic concepts-06-01.png)

------

<br>

## Logical Operators 02

- In the following example, we have connected two Boolean expressions with the **AND** operator.
  - 다음 예제에서, 두 개의 불리언 표현식을 **AND** 연산자로 연결했다.

```js
(4 > 2) && (10 < 15)
```

<br>

- For this expression to be **true**, both conditions must be **true**.
  - 이 표현식이 **true**가 되려면, 두 조건이 모두 **true**여야 한다.

<br>

1. The first condition determines whether 4 is greater than 2, which is **true**.
   - 첫 번째 조건은 4가 2보다 큰지 결정한다.
2. The second condition determines whether 10 is less than 15, which is also **true**.
   - 두 번째 조건은 10이 15보다 작은지도 결정한다.

<br>

- Based on these results, the whole expression is found to be **true**.
  - 이러한 결과를 바탕으로, 전체 표현식이 **true**라는 것을 알 수 있다.

<br>

#### Conditional (Ternary) Operator (삼항 연산자)

- Another JavaScript conditional operator assigns a value to a variable, based on some condition.
  - 다른 JavaScript 조건 연산자는 어떤 조건에 따라 변수에 값을 할당한다.

<br>

- Syntax:

```js
variable = (condition) ? value1 : value2
```

<br>

- For example:

```js
var isAdult = (age < 18) ? "Too young" : "Old enough";
```

<br>

- If the variable *age* is a value below 18, the value of the variable *isAdult* will be "Too young".
  - 변수 *age*가 18보다 적은 값인 경우, 변수 *isAdult*의 값은 "Too young"이다.
- Otherwise the value of *isAdult* will be "Old enough".
  - 그렇지 않으면 *isAdult*의 값은 "Old enough"이다.

<br>

> Logical operators allow you to connect as many expressions as you wish.
>
> 논리 연산자를 사용하면 원하는 만큼 많은 표현식을 연결할 수 있다.

------

<br>

## QUIZ

- Logical AND (&&) returns true if:
  - **Both operands are true**
  - If only one of the operands is true
  - If one of the operands is true, but not both

<br>

- Logical NOT returns true, if:
  - The operand is true
  - **The operand is false**

<br>