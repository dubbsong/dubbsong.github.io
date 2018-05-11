---
layout: post
title: "SoloLearn 번역 - 11. In-Place Operators (basic concepts)"
categories: dev
tags: python
---

## In-Place Operators (대입 연산자)

- **In-place operators** allow you to write code like 'x = x + 3' more concisely, as 'x += 3'.
  - **In-place** 연산자를 사용하면, 'x = x + 3'과 같은 코드를 'x += 3'과 같이 더 간결하게 작성할 수 있다.
- The same thing is possible with other operators such as -, *, / and % as well.
  - \-, *, /, %와 같은 다른 연산자에서도 동일한 작성이 가능하다.

```python
>>> x = 2
>>> print(x)
2

>>> x += 3
>>> print(x)
5
```

------

<br>

## In-Place Operators 02

- These operators can be used on types other than numbers, as well, such as **strings**.
  - 이 연산자는 문자열 이외의 숫자뿐만 아니라 타입에도 사용할 수 있다.

```python
>>> x = "spam"
>>> print(x)
spam

>>> x += "eggs"
>>> print(x)
spameggs
```

<br>

> Many other languages have special operators such as '++' as a shortcut for 'x += 1'.
>
> 다른 많은 언어에는 'x += 1'의 단축형으로 '++'와 같은 특수 연산자가 있다.

> Python **does not** have these.
>
> Python에는 이것들이 없다.

------

<br>

## QUIZ

- What is the output of this code?

```python
>>> x = 4
>>> x *= 3
>>> print(x)
12
```

<br>

- What is the result of this code?

```python
>>> x = "a"
>>> x *= 3
print(x)
aaa
```

<br>