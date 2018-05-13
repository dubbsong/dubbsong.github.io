---
layout: post
title: "SoloLearn 번역 - 03. finally (Exceptions & Files)"
categories: dev
tags: python
---

## finally (finally 문)

- To ensure some code runs no matter what errors occur, you can use a **finally** statement.
  - 에러가 발생하더라도 일부 코드가 실행되도록 하려면, **finally** 문을 사용할 수 있다.
- The **finally** statement is placed at the bottom of a **try/except** statement.
  - **finally** 문은 **try/except** 문의 맨 아래에 위치한다.
- Code within a **finally** statement always runs after execution of the code in the **try**, and possibly in the **except**, blocks.
  - **finally** 문 내의 코드는 **try**와 **except** 블록의 코드 실행 후 항상 실행된다.

```python
try:
   print("Hello")
   print(1 / 0)
except ZeroDivisionError:
   print("Divided by zero")
finally:
   print("This code will run no matter what")
```

<br>

- Result:

```python
>>>
Hello
Divided by zero
This code will run no matter what
>>>
```

<br>

## finally 02

- Code in a **finally** statement even runs if an uncaught exception occurs in one of the prededing blocks.
  - **finally** 문 내에서 코드는 앞선 블록 중 하나에서 catch 되지 않은 예외가 발생하더라도 실행된다.

```python
try:
   print(1)
   print(10 / 0)
except ZeroDivisionError:
   print(unknown_var)
finally:
   print("This is executed last")
```

<br>

- Result:

```python
>>>
1
This is executed last

ZeroDivisionError: division by zero
During handling of the above exception, another exception occurred:
NameError: name 'unknown_var' is not defined
>>>
```

<br>

## QUIZ

- What is the output of this code?
  - 3
  - 1 2 3
  - 1
  - **1 3**

```python
try:
   print(1)
except:
   print(2)
finally:
   print(3)
```

<br>

- Drag and drop from the options below to create a try/except/finally block.

```python
try:
   print(1)
except:
   print(2)
finally:
   print(42)
```

<br>