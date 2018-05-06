---
layout: post
title: "SoloLearn - 08. String Operations (basic concepts)"
categories: dev
tags: python
---

## Concatenation 01 (연결)

- As with integers and floats, string in Python can be added, using a process called `concatenation`, which can be done on any two strings.
  - 정수와 부동 소수점과 마찬가지로, 두 문자열에서 수행할 수 있는 `concatenation` 프로세스를 사용해서 Python의 문자열을 추가할 수 있다.
- When concatenating strings, it doesn't matter whether they've been created with single or double quotes.
  - 문자열을 연결할 때, 작은 따옴표나 큰 따옴표로 작성되었는지는 중요하지 않다.

```python
>>> "Spam" + 'eggs'
'Spameggs'

>>> print("First string" + ", " + "second string")
First string, second string
```

<br>

## Concatenation 02

- Even if your strings contain numbers, they are still added as strings rather than integers.
  - 문자열에 숫자가 포함되어 있더라도, 정수가 아닌 문자열로 계속 추가된다.
- Adding a string to a number produces an error, as even though they might look similar, they are two different entities.
  - 숫자에 문자열을 추가하면 에러가 발생한다. 비슷해 보이더라도, 다른 두 개체이다.

```python
>>> "2" + "2"
'22'

>>> 1 + '2' + 3 + '4'
Traceback(most recent call last):
   File "<stdin>", line 1, in <module>
TypeError. unsupported operand type(s) for +: 'int' and 'str'
```

<br>

> In future lessons, only the final line of error messages will be displayed, as it is the only one that gives details about the type of error that has occurred.
>
> 이후 강의에서는, 마지막 에러 메시지만 표시된다.

<br>

## String Operations

- Strings can also be **multiplied** by integers.
  - 문자열에 정수를 곱할 수도 있다.
- This produces a repeated version of the original string.
  - 원래 문자열의 반복 버전이 생성된다.
- The order of the string and the integer doesn't matter, but the string usually comes first.
  - 문자열과 정수의 순서는 중요하지 않지만, 일반적으로 문자열이 처음으로 온다.

<br>

- Strings can't be multiplied by other strings.
  - 문자열에는 다른 문자열을 곱할 수 없다.
- Strings also can't be multiplied by floats, even if the floats are whole numbers.
  - 부동 소수점이 정수라 해도, 문자열에 부동 소수점을 곱할 수 없다.

```python
>>> print("spam" * 3)
spamspamspam

>>> 4 * '2'
'2222'

>>> '17' * '87'
TypeError: can not multiply sequence by non-int of type 'str'
   
>>> 'pythonisfun' * 7.0
TypeError: can not multiply sequence by non-int of type 'float'
```

<br>

## QUIZ

- Fill in the missing string.

```python
>>> "Hello" + 'world'
'Hello world'
```

<br>

- Which line of code produces an error?
  - 3 + 4
  - **'5' + 6**
  - "7" + 'eight'
  - "one" + "2"

<br>

- What is the output of this code?

```python
>>> print(3 * '7')
'777'
```

<br>