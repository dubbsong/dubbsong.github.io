---
layout: post
title: "SoloLearn - 01. Booleans & Comparisons (Control Structures)"
categories: dev
tags: python
---

## Booleans (불리언)

- Another type in Python is the `Boolean` type.
  - Python의 또 다른 타입은 boolean 타입이다.
- There are two Boolean values: **True** and **False**.
  - 두 가지 boolean 값이 있다: **True**와 **False**.
- They can be created by comparing values, for instance by using the equal operator ==.
  - 값을 비교하는 비교 연산자 ==를 사용해서 생성할 수 있다.

```python
>>> my_boolean = True
>>> my_boolean
True

>>> 2 == 3
False
>>> "hello" == "hello"
True
```

<br>

> Be careful not to confuse **assignment** (one equals sign) with **comparison** (two equals signs).
>
> **할당**(등호 하나)과 **비교**(등호 두 개)를 혼동하지 않도록 주의해라.

------

<br>

## Comparison (비교)

- Another comparison operator, the **not equal** (!=), evaluates to **True** if the items being compared aren't equal, and **False** if they are.
  - 다른 비교 연산자인 **부등 비교 연산자**는, 비교되는 항목이 같지 않으면 **True**로 평가하고, 아니면 **False**로 평가한다.

```python
>>> 1! = 1
False

>>> "eleven" != "seven"
True

>>> 2 != 10
True
```

------

<br>

## Comparison 02

- Python also has operators that determine whether one number (float or integer) is greater than or smaller than another.
  - Python에는 하나의 숫자(부동 소수점 또는 정수)가 다른 숫자 보다 큰지 작은지 결정하는 연산자가 있다.
- These operators are > and < respectively.
  - 이 연산자는 각각 >와 < 연산자이다.

```python
>>> 7 > 5
True

>>> 10 < 10
False
```

------

<br>

## Comparison 02

- The greater than or equal to, and smaller than or equal to operators are >= and <=.
  - 크거나 같음, 작거나 같음 연산자는 >=와 <=이다.
- They are the same as the strict greater than and smaller than operators, except that they return True when comparing equal numbers.
  - 같은 숫자를 비교할 때 True를 반환한다는 것을 제외하고는, 크거나 같음과 작거나 같은 연산자와 동일한 규칙이다.

```python
>>> 7 <= 8
True

>>> 9 >= 9.0
True
```

<br>

> Greater than and smaller than operators can also be used to compare strings **lexicographically**.
>
> 크거나와 작거나 연산자는 사전 식으로 문자열을 비교할 수도 있다.

> (the alphabetical order of words is based on the alphabetical order of their component letters)
>
> 단어의 알파벳 순서는 구성 요소 문자의 알파벳 순서를 기반으로 한다.

------

<br>

## QUIZ

- What are the two Boolean values in Python?
  - true and false
  - **True and False**
  - Truth and Falsity

<br>

- What is the output of this code?

```python
>>> 7 != 8
True
```

<br>

- What is the output of this code?

```python
>>> 7 > 7.0
False
```

<br>

- What is the output of this code?

```python
>>> 8.7 <= 8.70
True
```

<br>