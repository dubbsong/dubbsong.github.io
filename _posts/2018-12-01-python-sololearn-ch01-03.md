---
layout: post
title: "(Basics 03) 간단한 연산"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- Python has the capability of carrying out calculations.
  - Python은 계산을 수행할 수 있다.
- Enter a calculation directly into the Python console, and it will output the answer.
  - Python 콘솔에 직접 계산을 입력하면 답이 출력된다.

```python
>>> 2 + 2
# 4

>>> 5 + 4 - 3
# 8
```

<br>

> The spaces around the plus and minus signs here are `optional` (the code would work without them), but they make it easier to read.
>
> \+와 \- 기호 주위의 공백은 `선택 사항`이다.
>
> 공백 없이 작동하지만, 공백이 있으면 가독성이 높아진다.

<br>

- Python also carries out multiplication and division, using an `asterisk` to indicate multiplication and a `forward slash` to indicate division.
  - Python은 곱셈과 나눗셈도 수행한다.
  - `*`는 곱셈을 나타내고, `/`는 나눗셈을 나타낸다.

<br>

- Use `parentheses` to determine which operations are performed first.
  - `괄호`를 사용해서 먼저 수행할 연산을 결정한다.

```python
>>> 2 * (3 + 4)
# 14

>>> 10 / 2
# 5.0
```

<br>

> Using a single slash to divide numbers produces a decimal (or `float`, as it is called in programming).
>
> slash(/)를 사용해서 숫자를 나누면 소수(또는 `부동 소수`)가 생성된다.

<br>

- The minus sign indicates a `negative number`.
  - \- 기호는 `음수`를 나타낸다.
- Operations are perfomed on negative numbers, just as they are on positive ones.
  - 양수와 마찬가지로, 음수에 대해서도 연산이 수행된다.

```python
>>> -7
# -7

>>> (-7 + 2) * (-4)
# 20
```

<br>

> The plus signs can also be put in front of numbers, but this has no effect, and is mostly used to emphasize that a number is positive to increase readability of code.
>
> \+ 기호도 숫자 앞에 놓을 수 있지만, 이는 아무 효과가 없다.
>
> 주로 코드의 가독성을 높이기 위해 숫자가 양수임을 강조하는 데 사용된다.

<br>

- Dividing by zero in Python produces an `error`, as no answer can be calculated.
  - Python에서 0으로 나누면 `에러`가 발생한다.
  - 답을 계산할 수 없다.

```python
>>> 11 / 0

# Traceback (most recent call last):
# File "<stdin>", line 1, in <module>
# ZeroDivisionError: division by zero
```

<br>

> In Python, the last line of an error message indicates the error's type.
>
> 에러 메시지의 마지막 줄은 에러 타입을 나타낸다.
>
> Read error messages carefully, as they often tell you how to fix a program.
>
> 에러 메시지는 프로그램을 어떻게 수정하는지 알려준다. 주의 깊게 읽어라.

<br>

<br>

#### QUIZ

- What does this code output?
  - 이 코드는 무엇을 출력하는가?

```python
>>> 1 + 2 + 3
```

> `6`

<br>

- Which option is output by this code?
  - 이 코드는 무엇을 출력하는가?

```python
>>> (4 + 8) / 2
```

> `6.0`

<br>

<br>