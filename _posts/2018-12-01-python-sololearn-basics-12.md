---
layout: post
title: "(Basics 12) 에디터 사용하기"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- So far, we've only used Python with the console, entering and running one line of code at a time.
  - 지금까지 콘솔로만 Python을 사용했다.
  - 한 번에 한 줄의 코드를 입력하고 실행했다.
- Actual programs are created differently; many lines of code are written in a file, and then executed with the Python interpreter.
  - 실제 프로그램은 다르게 생성된다.
  - 많은 코드 줄이 파일로 작성된 다음, Python 인터프리터(interpreter)로 실행된다.

> **interpreter:**
>
> a program that runs scripts written in an interpreted language such as Python
>
> Python과 같은 해석된 언어로 작성된 스크립트를 실행하는 프로그램

<br>

- In IDLE, this can be done by creating a new file, entering some code, saving the file, and running it.
  - IDLE에서 새로운 파일을 생성하고, 코드를 입력하고, 파일을 저장하고, 실행해서 작업을 수행할 수 있다.

> **IDLE:**
>
> an Integrated Development Environment for Python
>
> Python을 위한 통합 개발 환경

<br>

- Each line of code in the file is interpreted as though you entered it one line at a time at the console.
  - 파일의 각 코드 줄은 콘솔에서 한 번에 한 줄씩 입력된 것처럼 해석된다.

```python
>>> x = 7
>>> x = x + 2
>>> print(x)

# 9
```

[코드 실행 확인](https://code.sololearn.com/293/#py)

<br>

- Python source files have an extension of `.py`.
  - Python 소스 파일의 확장자는 `.py`이다.

<br>

<br>

#### QUIZ

- Which lines are executed when a Python file is run?
  - Python 파일이 실행될 때, 어떤 라인이 실행되는가?

> [] The first line only
>
> [] The first 100 lines
>
> [x] `Every line`

<br>

<br>