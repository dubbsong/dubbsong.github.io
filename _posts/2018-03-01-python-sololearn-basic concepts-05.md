---
layout: post
title: "SoloLearn 번역 - 05. Other Numerical Operations (basic concepts)"
categories: dev
tags: python
---

## Exponentiation (거듭제곱)

> `exponentiation`: rasing of one number to the power of another.

<br>

- Besides addition, subtraction, multiplication, and division, Python also supports `exponentiation`, which is the raising of one number to the power of another.
  - 덧셈, 뺄셈, 곱셈, 나눗셈 외에도 Python은 하나의 숫자를 다른 숫자의 멱승으로 올리는 거듭제곱 연산을 지원한다.
- This operation is performed using two asterisks.
  - 이 연산은 두 개의 별표(**)를 사용해서 수행된다.

```python
>>> 2**5
32

>>> 9 ** (1/2)
3.0
```

------

<br>

## Quotient & Remainder (몫 && 나머지)

- To determine the **quotient** and **remainder** of a division, use the **floor division** and **modulo** operators, respectively.
  - 나눗셈의 **몫**과 **나머지**를 결정하려면, 각각 **바닥 나눗셈**과 **모듈로** 연산자를 사용해라.
- Floor division is done using two forward slashes.
  - 바닥 나눗셈은 두 개의 사선(/)을 사용해서 수행된다.
- The modulo operator is carried out with a percent symbol(%).
  - 모듈로 연산자는 백분율 기호(%)로 수행된다.
- These operators can be used with both floats and integers.
  - 이 연산자들은 부동 소수점과 정수 모두에 사용할 수 있다.

<br>

- This code shows that 6 goes into 20 three times, and the remainder when 1.25 is divided by 0.5 is 0.25.
  - 이 코드는 6이 20으로 세 번 들어가고, 1.25를 0.5로 나눈 나머지는 0.25임을 보여준다.

```python
>>> 20 // 6
3

>>> 1.25 % 0.5
0.25
```

------

<br>

## QUIZ

- Fill in the blank to make this code correct.

```python
>>> (1 + 3) ** 2
16
```

<br>

- What is the result of this code?

```python
>>> 7 % (5 // 2)
1
```

<br>