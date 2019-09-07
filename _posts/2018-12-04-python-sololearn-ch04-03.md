---
layout: post
title: "(Exceptions & Files 03) finally 문"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- To ensure some code runs no matter what errors occur, you can use a `finally` statement.
  - 어떤 에러가 발생하더라도 일부 코드가 실행되도록 하기 위해 `finally` 문을 사용할 수 있다.
- The `finally` statement is placed at the bottom of a `try/except` statement.
  - `finally` 문은 `try/except` 문의 맨 아래에 위치한다.
- Code within a `finally` statement always runs after execution of the code in the `try`, and possibly in the `except`, blocks.
  - `finally` 문 내의 코드는, `try` 또는 `except` 코드를 실행한 후 항상 실행된다.

```python
try:
  print("Hello")
  print(1 / 0)
except ZeroDivisionError:
  print("Divided by zero")
finally:
  print("This code will run no matter what")
  
# Hello
# Divided by zero
# This code will run no matter what
```

[코드 실행 확인](https://code.sololearn.com/347/#py)

<br>

- Code in a `finally` statement even runs if an uncaught exception occurs in one of the preceding blocks.
  - `finally` 문의 코드는, 앞의 블록 중 하나에서 예외가 발생한 경우에도 실행된다.

```python
try:
  print(1)
  print(10 / 0)
except ZeroDivisionError:
  print(unknown_var)
finally:
  print("This is executed last")
  
# 1
# This is executed last

# ZeroDivisionError: division by zero
# During handling of the above exception, another exception occurred:
# NameError: name 'unknown_var' is not defined
```

[코드 실행 확인](https://code.sololearn.com/348/#py)

<br>

<br>

#### QUIZ

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
try:
  print(1)
except:
  print(2)
finally:
  print(3)
```

> `1 3`

<br>

- Drag and drop from the options below to create a try/except/finally block.
  - try/except/finally 블록을 생성해라.

```python
try:
  print(1)
except:
  print(2)
finally:
  print(42)
```

<br>

<br>