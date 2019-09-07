---
layout: post
title: "(Exceptions & Files 02) 예외 처리"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- To handle exceptions, and to call code when an exception occurs, you can use a `try/except` statement.
  - 예외를 처리하고, 예외가 발생했을 때 코드를 호출하기 위해, `try/except` 문을 사용할 수 있다.
- The `try` block contains code that might throw an exception.
  - `try` 블록은 예외를 발생시킬 수 있는 코드를 포함한다.
- It that exception occurs, the code in the `try` block stops being executed, and the code in the `except` block is run.
  - 해당 예외가 발생하면, `try` 블록의 코드 실행이 멈추고 `except` 블록의 코드가 실행된다.
- If no error occurs, the code in the `except` block doesn't run.
  - 에러가 발생하지 않으면, `except` 블록의 코드는 실행되지 않는다.

```python
try:
  num1 = 7
  num2 = 0
  print(num1 / num2)
  print("Done calculation")
except ZeroDivisionError:
  print("An error occurred")
  print("due to zero division")
  
# An error occurred
# due to zero division
```

[코드 실행 확인](https://code.sololearn.com/344/#py)

<br>

> In the code above, the except statement defines the type of exception to handle (in our case, the `ZeroDivisionError`).
>
> 위의 코드에서 except 문은, 처리할 예외 타입을 정의한다.

<br>

- A `try` statement can have multiple different `except` blocks to handle different exceptions.
  - `try` 문은 다른 예외를 처리하기 위해 여러 다른 `except` 블록을 가질 수 있다.
- Multiple exceptions can also be put into a single `except` block using parentheses, to have the `except` block handle all of them.
  - 괄호를 사용해서 하나의 `except` 블록에 여러 예외를 넣을 수 있다.

```python
try:
  variable = 10
  print(variable + "Hello")
  print(variable / 2)
except ZeroDivisionError:
  print("Divided by zero")
except (ValueError, TypeError):
  print("Error occurred")
  
# Error occurred
```

[코드 실행 확인](https://code.sololearn.com/345/#py)

<br>

- An `except` statement without any exception specified will catch all errors.
  - `except` 문은 모든 에러를 포착한다.
- These should be used sparingly, as they can catch unexpected errors and hide programming mistakes.
  - 예상치 못한 에러를 포착하고, 프로그래밍 실수를 숨길 수 있으므로, 삼가서 사용해야 한다.

```python
try:
  word = "spam"
  print(word / 0)
except:
  print("An error occurred")
  
#An error occurred
```

[코드 실행 확인](https://code.sololearn.com/346/#py)

<br>

> Exception handling is particularly useful when dealing with user input.
>
> 예외 처리는 사용자 입력을 처리할 때 특히 유용하다.

<br>

<br>

#### QUIZ

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
try:
  variable = 10
  print(10 / 2)
except ZeroDivisionError:
  print("Error")
  
print("Finished")
```

> `5.0 Finished`

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
try:
  meaning = 42
  print(meaning / 0)
  print("the meaning of life")
except (ValueError, TypeError):
  print("ValueError or TypeError occurred")
except ZeroDivisionError:
  print("Divided by zero")
```

> `Divided by zero`

<br>

- Fill in the blanks to handle all possible exceptions.
  - 가능한 모든 예외를 처리해라.

```python
try:
  num1 = input(":")
  num2 = input(":")
  print("float(num1) / float(num2)")
except:
  print("Invalid input")
```

<br>

<br>