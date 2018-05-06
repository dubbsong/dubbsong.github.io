---
layout: post
title: "SoloLearn - 04. Floats"
categories: dev
tags: python
---

## Floats 01

- **Floats** are used in Python to represent numbers that aren't integers.
  - Python에서 **부동 소수점**은 정수가 아닌 숫자를 나타내는 데 사용된다.
- Some examples of numbers that are represented as floats are 0.5 and -7.8237591.
  - 부동 소수점으로 나타내는 숫자의 예로는 0.5와 -7.8237591이 있다.
- They can be created directly by entering a number with a decimal point, or by using operations such as division on integers.
  - 소수점이 있는 숫자를 입력하거나 정수 나누기와 같은 연산을 사용해서 직접 만들 수 있다.
- Extra zeros at the number's end are ignored.
  - 숫자의 끝에 있는 추가 0은 무시된다.

```python
>>> 3/4
0.75

>>> 9.87650000
9.8765
```

<br>

> Computers can't store floats perfectly accurately, in the same way that we can't write down the complete deciaml expansion of 1/3 (0.3333333333333333…).
>
> 컴퓨터는 부동 소수점을 완전히 정확하게 저장할 수 없다. 1/3의 완전한 10진법 확장을 쓸 수 없는 것처럼.

<br>

## Floats 02

- As you saw previously, dividing any two integers produces a float.
  - 이전에 보았듯이, 두 정수를 나눌 경우 부동 소수점이 생긴다.
- A float is also produced by running an operation on two floats, or on a float and an integer.
  - 부동 소수점은 두 개의 부동 소수점 또는 부동 소수점과 정수를 연산해서 생성된다.

```python
>>> 8 / 2
4.0

>>> 6 * 7.0
42.0

>>> 4 + 1.65
5.65
```

<br>

> A float can be added to an integer, because Python silently converts the integer to a float.
>
> Python은 자동으로 정수를 부동 소수점으로 변환하므로, 부동 소수점을 정수에 추가할 수 있다.

> However, this implicit conversion is the exception rather the rule in Python - usually you have to convert values manually if you want to operate on them.
>
> 하지만, 이 암시형 변환은 Python의 규칙보다는 예외이다. 일반적으로 연산을 원할 경우 수동으로 값을 변환해야 한다.

<br>

## QUIZ

- Which of these will not be stored as a float?
  - **7**
  - 7.0
  - 2/4

<br>

- Fill in the blank with the output of this code.

```python
>>> 1 + 2 + 3 + 4.0 + 5
15.0
```

<br>