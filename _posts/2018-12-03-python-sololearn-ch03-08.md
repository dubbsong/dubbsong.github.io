---
layout: post
title: "(Functions & Modules 08) 표준 라이브러리 & pip"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

## Modules

###### 모듈

<br>

- There are three main types of modules in Python, those you write yourself, those you install from external sources, and those that are preinstalled with Python.
  - Python에는 세 가지 주요 타입의 모듈이 있다.
  - 직접 작성하는 모듈, 외부 소스로부터 설치하는 모듈, Python과 함께 사전 설치된 모듈이다.
- The last type is called the `standard library`, and contains many useful modules.
  - 마지막 타입을 `표준 라이브러리`라고 한다.
  - 유용한 모듈이 많이 있다.
- Some of the standard library's useful modules include `string`, `re`, `datetime`, `math`, `random`, `os`, `multiprocessing`, `subprocess`, `socket`, `email`, `json`, `doctest`, `unittest`, `pdb`, `argparse` and `sys`.
  - 표준 라이브러리의 유용한 모듈 중 일부는 다음과 같다.
  - `string`, `re`, `datetime`, `math`, `random`, `os`, `multiprocessing`, `subprocess`, `socket`, `email`, `json`, `doctest`, `unittest`, `pdb`, `argparse`, `sys` 등이다.
- Tasks that can be done by the standard library include string parsing, data serialization, testing, debugging and manipulating dates, emails, command line arguments, and much more!
  - 표준 라이브러리로 수행할 수 있는 작업에는 문자열 파싱, 데이터 직렬화, 테스트, 날짜 디버깅 및 조작, 이메일, 커맨드 라인 인수 등이 있다.

<br>

> Python's extensive standard library is one of its main strengths as a language.
>
> Python의 광범위한 표준 라이브러리는 언어로서의 주요 강점 중 하나이다.

<br>

## The Standard Library

###### 표준 라이브러리

<br>

- Some of the modules in the standard library are written in Python, and some are written in C.
  - 표준 라이브러리의 일부 모듈은 Python과 C로 작성된다.
- Most are available on all platforms, but some are Windows or Unix specific.
  - 대부분은 모든 플랫폼에서 사용 가능하지만, 일부는 Windows 또는 Unix 전용이다.

<br>

> We won't cover all of the modules in the standard library; there are simply too many.
>
> 표준 라이브러리의 모든 모듈을 다루지는 않는다. 너무 많다.
>
> The complete documentation for the standard library is available online at www.python.org.
>
> 표준 라이브러리에 대한 전체 문서는 www.python.org에서 제공된다.

<br>

## Modules

###### 모듈

<br>

- Many third-party Python modules are stored on the `Python Package Index (PyPI)`.
  - 많은 타사 Python 모듈은 `PyPI`에 저장된다.
- The best way to install these is using a program called `pip`.
  - 이를 설치하는 가장 좋은 방법은, `pip`라는 프로그램을 사용하는 것이다.
- This comes installed by default with modern distributions of Python.
  - 이는 최신 버전의 Python과 함께 기본으로 설치된다.
- If you don't have it, it is easy to install online.
  - 없는 경우, 온라인으로 쉽게 설치할 수 있다.
- Once you have it, installing libraries from `PyPI` is easy.
  - 일단 설치하면, `PyPI`에서 라이브러리를 쉽게 설치할 수 있다.
- Look up the name of the library you want to install, go to the command line (for Windows it will be the Command Prompt), and enter `pip install library_name`.
  - 설치하려는 라이브러리의 이름을 찾은 후, 커맨드 라인으로 이동하고, `pip install 라이브러리 이름`을 입력한다.
- Once you've done this, import the library and use it in your code.
  - 이 작업을 완료하면, 라이브러리를 import 하고 코드에서 사용한다.

<br>

> It's important to enter `pip` commands at the command line, not the Python interpreter.
>
> Python 인터프리터가 아닌 커맨드 라인에 `pip` 명령을 입력하는 것이 중요하다.

<br>

<br>

#### QUIZ

- Fill in the blanks to import the math module.
  - math 모듈을 import 해라.

```python
import math
```

<br>

- What name is given to Python's preinstalled modules?
  - Python의 사전 설치된 모듈의 이름은 무엇인가?

> `The Standard Library`

<br>

- What does PyPI stand for?
  - PyPI는 무엇의 약자인가?

> `Python Package Index`

<br>

<br>