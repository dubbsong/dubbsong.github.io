---
layout: post
title: "(Exceptions & Files 01) 예외"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- You have already seen `exceptions` in previous code.
  - 이전 코드에서 이미 `예외`를 보았다.
- They occur when something goes wrong, due to incorrect code or input.
  - 잘못된 코드나 입력으로 인해 문제가 있을 때 발생한다.
- When an exception occurs, the program immediately stops.
  - 예외가 발생하면 프로그램이 즉시 멈춘다.
- The following code produces the ZeroDivisionError exception by trying to divide 7 by 0.
  - 다음 코드는 7을 0으로 나누려고 해서 ZerodivisionError 예외가 발생한다.

```python
num1 = 7
num2 = 0
print(num1 / num2)

# ZeroDivisionError: division by zero
```

[코드 실행 확인](https://code.sololearn.com/343/#py)

<br>

- Different exceptions are raised for different reasons.
  - 다른 이유로 인해 다른 예외가 발생한다.

<br>

###### **Common exceptions:**

- `ImportError`: an import fails;
  - import를 실패했을 때 발생
- `IndexError`: a list is indexed with an out-of-range number;
  - 리스트가 범위를 벗어난 숫자로 색인화(indexed)될 때 발생
- `NameError`: an unknown variable is used;
  - 알수 없는 변수를 사용했을 때 발생
- `SyntaxError`: the code can't be parsed properly;
  - 코드를 제대로 파싱할 수 없을 때 발생
- `TypeError`: a function is called on a value of an inappropriate type;
  - 부적절한 타입의 값에 대해 함수가 호출되었을 때 발생
- `ValueError`: a function is called on a value of the correct type, but with an inappropriate value.
  - 올바른 타입의 값에서 함수가 호출되지만, 부적절한 값일 때 발생

<br>

> Python has several other built-in exceptions, such as ZeroDivisionError and OSError.
>
> Python에는 ZeroDivisionError 및 OSError와 같이 몇 가지 다른 내장 예외가 있다.
>
> Third-party libraries also often define their own exceptions.
>
> 타사 라이브러리도 종종 예외를 정의한다.

<br>

<br>

#### QUIZ

- What is an exception?
  - 예외란 무엇인가?

> An event that occurs due to incorrect code or input
>
> 잘못된 코드나 입력으로 인해 발생하는 이벤트이다.

<br>

- Which exception is raised by this code?
  - 이 코드에서 어떤 예외가 발생하는가?

```python
print("7" + 4)
```

> `TypeError`

<br>

<br>