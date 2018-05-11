---
layout: post
title: "SoloLearn 번역 - 05. Operator Precedence (Control Structures)"
categories: dev
tags: python
---

## Operator Precedence (연산자 우선순위)

- **Operator Precedence** is a very important concept in programming.
  - 연산자 우선순위는 프로그래밍에서 매우 중요한 개념이다.
- It is an extension of the mathematical idea of order of operations (multiplication being performed before addition, etc.) to include other operators, such as those in Boolean logic.
  - 연산자 우선순위는 다른 연산자를 포함하기 위해서 연산 순서(덧셈 전에 곱셈 수행 등)의 수학적 아이디어를 확장한 것이다. Boolean logic처럼.

<br>

- The below code shows that == has a higher precedence than **or**:
  - 아래 코드는 ==가 **or**보다 우선순위가 높음을 보여준다.

```python
>>> False == False or True
True

>>> False == (False or True)
False

>>> (False == False) or True
True
```

<br>

> Python's order of operations is the same as that of normal mathematics:
>
> Python의 연산 순서는 일반 수학과 동일하다.

> parentheses first, then exponentiation, then multiplication/division, and then addition/subtraction.
>
> 먼저 괄호가, 그 다음이 거듭제곱, 그 다음이 곱셈과 나눗셈, 그 다음이 덧셈과 뺄셈이다.

------

<br>

## Operator Precedence 02

- The following table lists all of Python's operators, from highest precedence to lowest.
  - 다음 표는 Python의 연산자를 나열한다. 높은 우선순위에서 낮은 우선순위까지.

![operatorTable](/assets/img/operatorTable.jpeg)

------

<br>

## QUIZ

- What is the result of this code?

```python
if 1 + 1 * 3 == 6:
   print("Yes")
else:
   print("No")
   
No
```

<br>

- What is the result of this code?

```python
x = 4
y = 2
if not 1 + 1 == y or x == 4 and 7 == 8:
   print("Yes")
elif x > y:
   print("No")
   
No
```

<br>