---
layout: post
title: "Python 3 Tutorial (SoloLearn)"
categories: dev
tags: python
---

## What is Python?

### Welcome to Python!

- **Python** is a high-level programming language,
  - **Python**은 고급 프로그래밍 언어이다.
- with applications in numerous areas,
  - 다양한 분야의 애플리케이션과 함께
- including web programming, scripting, scientific computing, and artificial intelligence.
  - 웹 프로그래밍, 스크립팅, 과학적인 컴퓨팅, 인공 지능을 포함하는

<br>

- It is very popular and used by organizations such as Google, NASA, the CIA, and Disney.
  - Google, NASA, CIA, Disney와 같은 조직에서 널리 사용한다.

>Python is processed at runtime by the interpreter.
>
>Python은 인터프리터에 의한 런타임에서 처리된다.

> There is no need to compile your program before executing it.
>
> 프로그램을 실행하기 전에 컴파일 할 필요가 없다.

<br>

- The three major versions of Python are 1.x, 2.x and 3.x.
  - Python의 주요 3가지 버전은 1.x, 2.x, 3.x이다.
- These are subdivided into mimor versions, such as 2.7 and 3.3.
  - 이들은 2.7과 3.3 같은 하위 버전으로 나눠진다.
- Code written for Python 3.x is guaranteed to work in all future versions.
  - Python 3.x로 작성된 코드는 이후 모든 버전에서 작동된다.
- Both Python Version 2.x and 3.x are used currently.
  - 현재 Python 버전 2.x와 3.x 모두 사용된다.
- This course covers **Python 3.x**, but it isn't hard to change from one version to another.
  - 이 코스는 **Python 3.x**를 다루지만, 한 버전에서 다른 버전으로 바꾸는 것은 어렵지 않다.

<br>

- Python has several different implementations, written in various languages.
  - Python은 다양한 언어로 작성된 몇 가지 다른 구현이 있다.
- The version used in this course, **CPython**, is the most popular by far.
  - 이 코스에서 사용하는 버전인 **CPython**은 가장 많이 사용하는 버전이다.

> An interpreter is a program that runs scripts written in an interpreted language such as Python.
>
> 인터프리터는 Python과 같이 해석된 언어로 작성된 스크립트를 실행하는 프로그램이다.

#### QUIZ

- Python is a:
  - Set of editing tools
  - **Programming language**
  - Development environment
- Which of these statements is true?
  - Python 1.7 is the most widely used version
  - Python code must be always compiled
  - **CPython is an implementation of Python**

<br>

## Your First Program

### Your First Program

- Let's start off by creating a short program that displays "Hello world!".
  - "Hello world!"가 표시되는 짧은 프로그램을 만들어보자.
- In Python, we use the **print** statement to output text:
  - Python에서는, **print** 문을 사용해서 텍스트를 출력한다:

```python
>>> print('Hello world!')
```

<br>

- Congratulations! You have written your first program.
  - 축하한다. 첫 프로그램을 작성해보았다.

> Run, save, and share your Python code on our **Code Playground** without installing any additional software.
>
> 추가 소프트웨어를 설치하지 않고 **Code Playground**에서 Python 코드를 실행, 저장, 공유해라.

> When using a computer, you will need to download and install Python from www.python.org.
>
> 컴퓨터를 사용할 때는, www.python.org에서 Python을 다운로드하고 설치해야 한다.

> Note the >>> in the code above.
>
> 위의 코드에서 >>>를 주의해라.

> They are the prompt symbol of the Python console.
>
> Python 콘솔의 prompt symbol이다.

> Python is an interpreted language, which means that each line is executed as it is entered.
>
> Python은 해석된 언어이다. 즉, 각 라인은 입력한 대로 실행된다.

> Python also includes <u>IDLE</u>, the integrated development environment, which includes tools for writing and debugging entire programs.
>
> Python은 프로그램 작성과 디버깅을 위한 통합 개발 환경인 <u>IDLE</u>이 포함되어 있다.

<br>

### Printing Text

- The **print** statement can also be used to output multiple lines of text.
  - **print** 문은 여러 줄의 텍스트를 출력하는 데에도 사용할 수 있다.
- For Example:

```python
>>> print('Hello world!')
Hello world!

>>> print('Hello world!')
Hello world!

>>> print('Spam and eggs...')
Spam and eggs
```

<br>

> Python code often contains references to the comedy group **Monty Python**.
>
> Python 코드는 종종 코미디 그룹 **Monty Python**에 대한 참조를 포함한다.

> This is why the words, "spam" and "eggs" are often used as placeholder variables in Python where "foo" and "bar" would be used in other programming languages.
>
> Python에서 "spam"과 "eggs"가 placeholder 변수로 종종 사용되는 이유는 "foo"와 "bar"가 다른 프로그래밍 언어에서 사용되는 것과 비슷하다.

<br>

#### QUIZ

- Fill in the blanks to print "Hi".
  - "Hi"를 출력하도록 빈칸을 채워라.

```python
>>> print('Hi')
```

- Fill in the blank to output "ni ni ni".
  - "ni ni ni"가 출력되도록 빈칸을 채워라.

```python
>>> print('ni ni ni')
```

<br>

## Simple Operations

### Simple Operations

- 