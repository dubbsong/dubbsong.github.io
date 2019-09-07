---
layout: post
title: "(Exceptions & Files 04) raise 문"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

## Raising Exceptions

###### 예외 발생시키기

<br>

- You can raise exceptions by using the `raise` statement.
  - `raise` 문을 사용해서 예외를 발생시킬 수 있다.

```python
print(1)
raise ValueError
print(2)

# 1
# ValueError
```

[코드 실행 확인](https://code.sololearn.com/349/#py)

<br>

> You need to specify the `type` of the exception raised.
>
> 발생하는 예외 `타입`을 지정해야 한다.

<br>

- Exceptions can be raised with arguments that give detail about them.
  - 세부 사항을 제공하는 인수로 예외를 발생시킬 수 있다.

```python
name = "123"
raise NameError("Invalid name!")

# NameError: Invalid name!
```

[코드 실행 확인](https://code.sololearn.com/350/#py)

<br>

<br>

#### QUIZ

- Which errors occur during the execution of this code?
  - 이 코드를 실행하는 동안 어떤 에러가 발생하는가?

```python
try:
  print(1 / 0)
except ZeroDivisionError:
  raise ValueError
```

> `ZeroDivisionError ValueError`

<br>

- Fill in the blanks to raise a ValueError exception, if the input is negative.
  - 입력이 음수인 경우, ValueError 예외를 발생시켜라.

```python
num = input(":")

if float(num) < 0:
  raise ValueError("Negative!")
```

<br>

<br>