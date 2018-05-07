---
layout: post
title: "SoloLearn - 04. Boolean Logic (Control Structures)"
categories: dev
tags: python
---

## Boolean Logic

- Boolean logic is used to make more complicated conditions for if statements that rely on more than one condition.
  - Boolean logic은 하나 이상의 조건에 의존하는 if 문에 대해 더 복잡한 조건을 만드는 데 사용된다.
- Python's Boolean operators are **and**, **or**, and **not**.
  - Python의 Boolean 연산자는 **and**, **or**, **not**이다.
- The **and** operator takes two arguments, and evaluates as **True** if, and only if, both of its arguments are **True**.
  - **and** 연산자는 두 개의 인수를 취하고, 두 인수가 모두 **True**인 경우에만 **True**로 평가한다.
- Otherwise, it evaluates to **False**.
  - 그렇지 않으면, **False**로 평가한다.

```python
>>> 1 == 1 and 2 == 2
True

>>> 1 == 1 and 2 == 3
False

>>> 1 != 1 and 2 == 2
False

>>> 2 < 1 and 3 > 6
False
```

<br>

> Python uses words for its Boolean operators, whereas most other languages use symbols such as &&, || and !.
>
> Python은 Boolean 연산자에 단어를 사용하지만, 대부분의 다른 언어는 &&, ||, ! 같은 기호를 사용한다.

------

<br>

## Boolean Or

- The **or** operator also takes two arguments.
  - **or** 연산자도 두 개의 인수를 취한다.
- It evaluates to **True** if either (or both) of its arguments are **True**, and **False** if both arguments are **False**.
  - 인수 중 하나(또는 둘 다)가 True면 **True**로 평가되고, 두 인수가 모두 False면 **False**로 평가된다.

```python
>>> 1 == 1 or 2 == 2
True

>>> 1 == 1 or 2 == 3
True

>>> 1 != 1 or 2 == 2
True

>>> 2 < 1 or 3 > 6
False
```

------

<br>

## Boolean Not

- Unlike other operators we've seen so far, **not** only takes one argument, and inverts it.
  - 지금까지 본 다른 연산자와는 다르게, **not**은 하나의 인수만 취하고, 반전시킨다.
  - `argument`: a value passed to a function (or method) when calling it.
- The result of **not True** is **False**, and **not False** goes to **True**.
  - **not True**의 결과는 **False**이고, **not False**의 결과는 **True**이다.

```python
>>> not 1 == 1
False

>>> not 1 > 7
True
```

<br>

> You can chain multiple conditional statements in an if statement using the Boolean operators.
>
> Boolean 연산자를 사용해서 if 문에 여러 조건문을 연결할 수 있다.

------

<br>

## QUIZ

- What is the result of this code?

```python
if (1 == 1) and (2 + 2 > 3):
   print("true")
else:
   print("false")
   
true
```

<br>

- Fill in the blanks to print "Welcome".

```python
age = 15
money = 500
if age > 18 or money > 100
	print("Welcome")
```

<br>

- What is the result of this code?

```python
if not True:
   print("1")
elif not (1 + 1 == 3):
   print("2")
else:
   print("3")
   
2
```

<br>