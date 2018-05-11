---
layout: post
title: "SoloLearn 번역 - 01. Exceptions (Exceptions & Files)"
categories: dev
tags: python
---

## Exceptions (예외)

- You have already seen **exceptions** in previous code.
  - 이전 코드에서 이미 **예외**를 보았다.
- They occur when something goes wrong, due to incorrect code or input.
  - 예외는 부정확한 코드로 무언가가 잘못되거나 입력으로 인한 문제 때문에 발생한다.
- When an exception occurs, the program immediately stops.
  - 예외가 발생하면, 프로그램은 즉시 정지된다.
  - `exception`: means of breaking out of the normal flow of control of a code block in order to handle errors or other exceptional conditions.
- The following code produces the ZeroDivisionError exception by trying to divide 7 by 0.
  - 다음 코드는 7을 0으로 나누려고 하기 때문에 ZeroDivisionError 예외를 생성한다.

```python
num1 = 7
num2 = 0
print(num1/num2)
```

<br>

- Result:

```python
>>>
ZeroDivisionError: division by zero
>>>
```

------

<br>

## Exceptions 02

- Different exceptions are raised for different reasons.
  - 다른 이유로 인해 다른 예외가 발생한다.
- Common exceptions:
  - 일반적인 예외들:

> **ImportError**: an import fails;
>
> 가져오기를 실패했을 때;

> **IndexError**: a list is indexed with an out-of-range number;
>
> 배열이 범위를 벗어난 숫자로 인덱싱되었을 때;

> **NameError**: an unknown variable is used;
>
> 알 수 없는 변수가 사용되었을 때;

> **SyntaxError**: the code can't be parsed properly;
>
> 코드를 제대로 파싱할 수 없을 때;

> **TypeError**: a function is called on a value of an inappropriate type;
>
> 함수가 부적절한 타입의 값에 의해 호출되었을 때;
>
> **ValueError**: a function is called on a value of the correct type, but with an inappropriate value.
>
> 함수가 올바른 타입의 값에 의해 부적절한 값으로 호출되었을 때;

<br>

> Python has several other built-in exceptions, such as ZeroDivisionError and OSError.
>
> Python에는 ZeroDivisionError와 OSError와 같은 몇 가지 내장된 예외가 있다.

> Third-party libraries also often define their own exceptions.
>
> 타사 라이브러리는 종종 자체 예외를 정의한다.

------

<br>

## QUIZ

- What is an exception?
  - A variable
  - **An event that occurs due to incorrect code or input**
  - A function

<br>

- Which exception is raised by this code?
  - ZeroDivisionError
  - **TypeError**
  - ValueError

```python
print("7" + 4)
```

<br>