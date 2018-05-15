---
layout: post
title: "SoloLearn 번역 - 02. Exception Handling (Exceptions & Files)"
categories: dev
tags: python
---

## Exception Handling (예외 처리)

- To handle exceptions, and to call code when an exception occurs, you can use a **try/except** statement.
  - 예외를 처리하고, 예외가 발생했을 때 코드를 호출하는 것은, **try/except** 문을 사용할 수 있다.
  - `exception`: means of breaking out of the normal flow of control of a code block in order to handle errors or other exceptional conditions.
- The **try** block contains code that might throw an exception.
  - **try** 블록은 예외를 처리할 수 있는 코드를 포함한다.
- If that exception occurs, the code in the **try** block stops being executed, and the code in the **except** block is run.
  - 만약 예외가 발생하면, **try** 블록 안의 코드가 정지되고, **except** 블록의 코드가 실행된다.
- If no error occurs, the code in the **except** block doesn't run.
  - 만약 오류가 발생하지 않으면, **except** 블록 안의 코드는 실행되지 않는다.

<br>

- For example:

```python
try:
   num1 = 7
   num2 = 0
   print("Done calculation")
except ZeroDivisionError:
   print("An error occurred")
   print("due to zero division")
```

<br>

- Result:

```python
>>>
An error occurred
due to zero division
>>>
```

<br>

> In the code above, the except statement defines the type of exception to handle (in our case, the **ZeroDivisionError**).
>
> 위의 코드에서, except 문은 처리할 예외 타입을 정의한다 (이 경우에는, **ZeroDivisionError**).

------

<br>

## Exception Handling 02

- A **try** statement can have multiple different **except** blocks to handle different exceptions.
  - **try** 문은 여러 다른 예외 처리를 하기 위해 다른 **except** 블록을 가질 수 있다.
- Multiple exceptions can also be put into a single **except** block using parentheses, to have the **except** block handle all of them.
  - 여러 예외들은 괄호를 사용해서 하나의 **except** 블록에 넣을 수도 있다. **except** 블록이 모두 처리하도록.

```python
try:
   variable = 10
   print(variable + "hello")
   print(variable / 2)
except ZeroDivisionError:
   print("Divided by zero")
except (ValueError, TypeError):
   print("Error occurred")
```

<br>

- Result:

```python
>>>
Error occurred
>>>
```

------

<br>

## Exception Handling 03

- An **except** statement without any exception specified will catch all errors.
  - 예외가 지정되지 않은  **except** 문은 모든 에러를 catch한다.
- These should be used sparingly, as they can catch unexpected errors and hide programming mistakes.
  - 예기치 않은 오류를 catch하고 프로그래밍 실수를 숨길 수 있으므로, 이러한 코드는 드물게 사용해야 한다.

<br>

- For example:

```python
try:
   word = "spam"
   print(word / 0)
except:
   print("An error occurred")
```

<br>

- Result:

```python
>>>
An error occurred
>>>
```

<br>

> Exception handling is particularly useful when dealing with user input.
>
> 예외 처리는 유저 입력을 처리할 때 특히 유용하다.

------

<br>

## QUIZ

- What is the output of this code?
  - **5.0 Finished**
  - 5.0
  - Error Finished

```python
try:
   variable = 10
   print(10 / 2)
except ZeroDivisionError:
   print("Error")
print("Finished")
```

<br>

- What is the output of this code?
  - Divided by zero ValueError or TypeError occurred
  - ValueError or TypeError occurred
  - **Divided by zero**

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

<br>

- Fill in the blanks to handle all possible exceptions.

```python
try:
   num1 = input(":")
   num2 = input(":")
   print(float(num1)/float(num2))
except:
   print("Invalid input")
```

<br>