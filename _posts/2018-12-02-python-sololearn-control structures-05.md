---
layout: post
title: "(Control Structures 05) 연산자 우선순위"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- `Operator precedence` is a very important concept in programming.
  - `연산자 우선순위`는 프로그래밍에서 매우 중요한 개념이다.
- It is an extension of the mathematical idea of order of operations (multiplication being performed before addition, etc.) to include other operators, such as those in Boolean logic.
  - 이는 다른 연산자를 포함하기 위해, 연산 순서의 수학적 개념을 확장한 것이다.
- The below code shows that == has a higher precedence than `or`:
  - 아래 코드는 ==가 `or`보다 우선순위가 높다는 것을 보여준다.

```python
>>> False == False or True
# True

>>> False == (False or True)
# False

>>> (False == False) or True
# True
```

[코드 실행 확인](https://code.sololearn.com/306/#py)

<br>

> Python's order of operations is the same as that of normal mathematics: parentheses first, then exponentiation, then multiplication/division, and then addition/subtraction.
>
> Python의 연산 순서는 일반 수학의 순서와 같다.
>
> 괄호를 먼저 연산하고, 그 다음 지수, 그 다음 곱셈/나눗셈, 그 다음 덧셈/뺄셈이다.

<br>

- The following table lists all of Python's operators, from highest precedence to lowest.
  - 다음 표는 모든 Python의 연산자를 높은순에서 낮은순으로 나열한다.

![img](/assets/img/python-sololearn-control structures-05-01.jpeg)

<br>

<br>

#### QUIZ

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
if 1 + 1 * 3 == 6:
  print("Yes")
else:
  print("No")
```

> `No`

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
x = 4
y = 2

if not 1 + 1 == y or x == 4 and 7 == 8:
  print("Yes")
elif x > y:
  print("No")
```

> `No`

<br>

<br>