---
layout: post
title: "SoloLearn - 03. Simple Operations (basic concepts)"
categories: dev
tags: python
---

## Simple Operations (기본 연산자)

- Python has the capability of carrying out calculations.
  - Python에는 계산을 수행할 수 있는 기능이 있다.
- Enter a calculation directly into the Python console, and it will output the answer.
  - Python 콘솔에 직접 계산을 입력하면, 답이 출력될 것이다.

```python
>>> 2 + 2
4

>>> 5 + 4 - 3
6
```

<br>

> The spaces around the plus and minus signs here are **optional** (the code would work without them), but they make it easier to read.
>
> 플러스와 마이너스 기호 주변 공백은 **선택 사항**이지만, 공백을 사용하면 가독성이 좋다.

------

<br>

## Simple Operations 02

- Python also carries out multiplication and division,
  - Python은 곱셈과 나눗셈 또한 수행한다.
- using an **asterisk** to indicate multiplication and a **forward slash** to indicate division.
  - 곱셈을 나타내는 **별표(*)**와 나눗셈을 나타내는 **사선(/)**을 사용한다.

<br>

- Use **parentheses** to determine which operations are performed first.
  - **괄호**를 사용해서 먼저 수행할 연산을 결정한다.

```python
>>> 2 * (3 + 4)
14

>>> 10 / 2
5.0
```

<br>

> Using a single slash to divide numbers produces a decimal (or **float**, as it is called in programming).
>
> 단일 사선을 사용해서 숫자를 나누면 10진수(또는 **부동 소수점**)가 생성된다.

> We'll have more about **floats** in a later lesson.
>
> 나중 수업에서 부동 소수점에 대해 더 알아볼 것이다.

------

<br>

## Simple Operations 03

- The minus sign indicates a **negative** number.
  - 마이너스 기호는 **음수**를 나타낸다.
- Operations are perfomed on negative numbers, just as they are on positive ones.
  - 연산은 양수와 마찬가지로 음수로 수행된다.

```python
>>> -7
-7

>>> (-7 + 2) * (-4)
20
```

<br>

> The plus signs can also be put in front of numbers, but this has no effect, and is mostly used to emphasize that a number is positive to increase readability of code.
>
> 더하기 기호는 숫자 앞에 놓을 수 있지만, 아무 효과가 없다.
>
> 그리고 코드의 가독성을 높이기 위해 숫자가 양수임을 강조하는 데에 주로 사용된다.

------

<br>

## Simple Operations 04

- Dividing by zero in Python produces an **error**, as no answer can be calculated.
  - Python에서 0으로 나누면 아무 답도 계산되지 않으므로, **에러**가 발생한다.

```python
>>> 11 / 0
Traceback(most recent call last):
   File "<stdin>", line 1, in <module>
ZeroDivisionError: division by zero
```

<br>

> In Python, the last line of an error message indicates the error's type.
>
> Python에서, 에러 메시지의 마지막 라인은 에러의 유형을 나타낸다.

> Read error messages carefully, as they often tell you how to fix a program!
>
> 주의해서 에러 메시지를 읽어라. 프로그램을 어떻게 수정할지 종종 알려준다.

------

<br>

## QUIZ

- What does this code output?

```python
>>> 1 + 2 + 3
6
```

<br>

- Which option is output by this code?

```python
>>> (4 + 8) / 2
6.0
```

> `6`이 아닌 `6.0`이 출력된다.

<br>

- Fill in the blank to make this code correct.

```python
>>> (-5 - 1) * 3
-18
```

<br>

- Drag and drop the answer that will cause a ZeroDivisionError.

```python
>>> (17 + 94) / (-5 + 5)
```

<br>