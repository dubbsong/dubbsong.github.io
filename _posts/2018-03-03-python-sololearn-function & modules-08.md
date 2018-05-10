---
layout: post
title: "SoloLearn - 08. The Standard Library & pip (Function & Module)"
categories: dev
tags: python
---

## Modules

- There are three main types of modules in Python, those you write yourself, those you install from external sources, and those that are preinstalled with Python.
  - Python에는 3가지 주요한 모듈의 타입이 있다. 그것은 직접 작성하는 타입, 외부 소스에서 설치하는 타입, Python이 기본으로 설치한 타입이다.
- The last type is called the **standard library**, and contains many useful modules.
  - 마지막 타입은 **standard library**라고 부르며, 많은 유용한 모듈을 포함한다.
- Some of the standard library's useful modules include **string, re, datetime, math, random, os, multiprocessing, subprocess, socket, email, json, doctest, unittest, pdb, argparse and sys.**
  - standard library의 유용한 모듈에는 **string, re, datetime, math, random, os, multiprocessing, subprocess, socket, email, json, doctest, unittest, pdb, argparse, sys**가 있다.

<br>

- Tasks that can be done by the standard library include string parsing, data serialization, testing, debugging and manipulating dates, emails, command line arguments, and much more!
  - standard library에서 수행할 수 있는 작업으로는 string parsing, data serialization, testing, debugging and manipulating dates, emails, command line arguments 등이 있다.

<br>

> Python's extensive standard library is one of its main strengths as a language.
>
> Python의 광범위한 standard library는 언어로서의 주요 강점 중 하나이다.

<br>

## The Standard Library

- Some of the modules in the standard library are written in Python, and some are written in C.
  - standard library의 일부 모듈은 Python으로 작성되고, 일부는 C로 작성된다.
- Most are available on all platforms, but some are Windows or Unix specific.
  - 대부분은 플랫폼에서 사용할 수 있지만, 일부는 Windows 또는 Unix에서만 사용할 수 있다.

<br>

> We won't cover all of the modules in the standard library; there are simply too many.
>
> 우리는 standard library의 모든 모듈을 다루지는 않을 것이다. 단순히 너무 많다.

> The complete documentation for the standard library is available online at www.python.org.
>
> standard library에 대한 전체 문서는 www.python.org에서 온라인으로 볼 수 있다.

<br>

## Modules 02

- Many third-party Python modules are stored on the **Python Package Index** (PyPI).
  - 많은 타사 Python 모듈은 **Python Package Index**(PyPI)에 저장된다.
- The best way to install these is using a program called **pip**.
  - 이를 설치하는 가장 좋은 방법은 **pip**라는 프로그램을 사용하는 것이다.
- This comes installed by default with modern distributions of Python.
  - 이는 최신 Python 배포판에 기본적으로 설치된다.
- If you don't have it, it is easy to install online.
  - 만약 가지고 있지 않다면, 온라인으로 쉽게 설치할 수 있다.
- Once you have it, installing libraries from PyPI is easy.
  - 일단 한 번 해보면, PyPI에서 라이브러리를 설치하는 것은 쉽다.
- Look up the name of the library you want to install, go to the command line (for Windows it will be the Command Prompt), and enter **pip install library_name**.
  - 설치하려는 라이브러리의 이름을 찾은 후 커맨드 라인(Windows의 경우 Command Prompt)으로 이동해서 **pip install library_name**을 입력해라.
- Once you've done this, import the library and use it in your code.
  - 이 작업을 완료하면, 라이브러리를 가져와 코드 내부에서 사용해라.

<br>

- Using **pip** is the standard way of installing libraries on most operating systems, but some libraries have prebuilt binaries for Windows.
  - **pip**를 사용하는 것은 대부분의 운영 체제에서 설치의 표준 방법이지만, 일부 라이브러리에는 Windows 용 사전 빌드 바이너리가 있다.
- These are normal executable files that let you install libraries with a GUI the same way you would install other programs.
  - 이것들은 GUI를 사용해서 다른 프로그램을 설치할 때와 같은 방식으로 라이브러리를 설치할 수 있게 해주는 일반 실행 파일이다.

<br>

> It's important to enter **pip** commands at the command line, not the Python interpreter.
>
> 이것은 Python 인터프리터가 아닌, 커맨드 라인에서 **pip** 명령을 입력하는 것이 중요하다.

<br>

## QUIZ

- Fill in the blanks to import the math module.
  - **import math**

<br>

- What name is given to Python's preinstalled modules?
  - **The Standard Library**
  - import
  - Unix

<br>

- What does PyPI stand for?
  - **Python Package Index**
  - Python Package Installer
  - Python Project Index

<br>