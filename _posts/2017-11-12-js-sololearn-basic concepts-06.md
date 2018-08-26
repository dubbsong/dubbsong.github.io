---
layout: post
title: "06. 논리 연산자 or 불리언 연산자 (Basic Concepts)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript Logical or Boolean Operators

###### JavaScript 논리 연산자 or 불리언 연산자

------

<br><br>

## Logical Operators

###### 논리 연산자

<br>

- `Logical` Operators, also known as `Boolean` Operators, evaluate the expression and return `true` or `false`.
  - `Boolean` 연산자라고도 하는 `논리` 연산자는 표현식을 평가하고, `true` 또는 `false`를 반환한다.

<br>

- The table below explains the logical operators (`AND`, `OR`, `NOT`).
  - 아래 테이블은 논리 연산자(`AND`, `OR`, `NOT`)를 설명한다.

![sololearn img](/assets/img/sololearn-js-basic concepts-06-01.png)

<br>

<br>

- In the following example, we have connected two Boolean expressions with the `AND` operator.
  - 다음 예제에서는, 두 개의 Boolean 표현식을 `AND` 연산자로 연결했다.

```js
(4 > 2) && (10 < 15)
```

[코드 실행 확인 링크](https://code.sololearn.com/657/#js)

<br>

- For this expression to be `true`, both conditions must be `true`.
  - 이 표현식이 `ture`가 되려면, 두 조건이 모두 `true` 여야 한다.
- The first condition determines whether 4 is greater than 2, which is `true`.
  - 첫 번째 조건은 4가 2보다 큰지를 결정한다.
- The second condition determines whether 10 is less than 15, which is also `true`.
  - 두 번째 조건은 10이 15보다 작은지를 결정한다.
- Based on these results, the whole expression is found to be `true`.
  - 이러한 결과를 바탕으로, 전체 표현식이 `true`로 밝혀졌다.

<br>

#### Conditional (Ternary) Operator

###### 조건부(3항) 연산자

<br>

- Another JavaScript conditional operator assigns a value to a variable, based on some condition.
  - 또 다른 JavaScript 조건 연산자는 어떤 조건에 따라 변수에 값을 할당한다.

<br>

- Syntax:

```js
variable = (condition) ? value1 : value2
```

<br>

- For example:

```js
var age = 42;
var isAdult = (age < 18) ? "Too young" : "Old enough";
document.write(isAdult);
```

[코드 실행 확인 링크](https://code.sololearn.com/658/#js)

<br>

- If the variable *age* is a value below 18, the value of the variable *isAdult* will be "Too young".
  - 변수 *age*가 18 미만의 값인 경우, 변수 *isAdult*의 값은 "Too young"이다.
- Otherwise the value of *isAdult* will be "Old enough".
  - 그렇지 않으면 *isAdult*의 값은 "Old enough"가 된다.

<br>

> Logical operators allow you to connect as many expressions as you wish.
>
> 논리 연산자를 사용하면 원하는 만큼 많은 표현식을 연결할 수 있다.

------

<br>

## QUIZ

- Logical AND (&&) returns true if:
  - 논리 AND(&&)는 다음과 같은 경우 true를 반환한다.

> `Both operands are true`
>
> 두 연산자 모두 참일 때

<br>

- Logical NOT returns true, if:
  - 논리 NOT은 다음과 같은 경우 true를 반환한다.

> `The operand is false`
>
> 피연산자가 false일 때

<br>