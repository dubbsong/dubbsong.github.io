---
layout: post
title: "SoloLearn 번역 - 04. Raising Exceptions (Exceptions & Files)"
categories: dev
tags: python
---

## Raising Exceptions (예외 발생)

- You can raise exceptions by using the **raise** statement.
  - **raise** 문을 사용해서 예외를 발생시킬 수 있다.

```python
print(1)
raise ValueError
print(2)
```

<br>

- Result:

```python
>>>
1
ValueError
>>>
```

<br>

> You need to specify the **type** of the exception raised.
>
> 발생된 예외의 타입을 지정해야 한다.

------

<br>

## Raising Exceptions 02

- Exceptions can be raised with arguments that give detail about them.
  - 예외는 세부 사항을 제공하는 인수로 발생될 수 있다.

<br>

- For example:

```python
name = "123"
raise NameError("Invalid name!")
```

<br>

- Result:

```python
>>>
NameError: Invalid name!
>>>
```

------

<br>

## Raising Exceptions

- In **except** blocks, the **raise** statement can be used without arguments to re-raise whatever exception occurred.
  - **except** 블록에서는, **raise** 문을 인수 없이 사용해서 발생한 예외를 다시 발생시킬 수 있다.

<br>

- For example:

```python
try:
   num = 5 / 0
except:
   print("An error occurred")
   raise
```

<br>

- Result:

```python
>>>
An error occurred

ZeroDivisionError: division by zero
>>>
```

------

<br>

## QUIZ

- Which errors occur during the execution of this code?
  - **ZeroDivisionError and ValueError**
  - ValueError
  - none
  - ZeroDivisionError

```python
try:
   print(1 / 0)
except ZeroDivisionError:
   raise ValueError
```

<br>

- Fill in the blanks to raise a ValueError exception, if the input is negative.

```python
num = input(":")
if float(num) < 0:
   raise ValueError("Negative!")
```

<br>

- Can you use the raise statement outside the except block?
  - No
  - **Yes**

<br>