---
layout: post
title: "(Basics 05) 지수 연산, 몫 & 나머지 연산"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

#### Exponentiation

###### 지수 연산

- Besides addition, subtraction, multiplication, and division, Python also supports `exponentiation`, which is the raising of one number to the power of another.
  - Python은 더하기, 빼기, 곱하기, 나누기 외에도 `지수 연산`을 지원한다.
  - 지수 연산은 한 숫자를 다른 숫자의 거듭제곱으로 올리는 것이다.
- This operation is performed using two asterisks.
  - 지수 연산은 두 개의 별표(\*)를 사용해서 수행된다.

```python
>>> 2 ** 5
# 32

>>> 9 ** (1/2)
# 3.0
```

<br>

<br>

#### Quotient \& Remainder

###### 몫 \& 나머지

- To determine the `quotient` and `remainder` of a division, use the `floor division` and `modulo operators`, respectively.
  - 나눗셈의 `몫`을 얻으려면, `floor division(정수 나눗셈)`을 사용한다.
  - 나눗셈의 `나머지`를 얻으려면, `modulo operators(나머지 연산자)`를 사용한다.
- Floor division is done using two forward slashes.
  - 정수 나눗셈은 두 개의 슬래시(`//`)를 사용해서 수행한다.
- The modulo operator is carried out with a percent symbol.
  - 나머지 연산자는 퍼센트 기호(`%`)를 사용해서 수행한다.
- These operators can be used with both floats and integers.
  - 나머지 연산자는 float과 정수 모두에 사용할 수 있다.

<br>

- For example:

```python
>>> 20 // 6
# 3

>>> 1.25 % 0.5
# 0.25
```

<br>

<br>

#### QUIZ

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
>>> 7 % (5 // 2)
```

> `1`

<br>

<br>