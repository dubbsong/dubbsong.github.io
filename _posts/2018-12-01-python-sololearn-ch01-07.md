---
layout: post
title: "(Basics 07) 입력과 출력"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- Usually, programs take `input` and process it to produce `output`.
  - 프로그램은 일반적으로 `입력(input)`을 받아 처리하고, `출력(output)`을 생성한다.
- In Python, you can use the `print` function to produce output.
  - Python에서는, `print` 함수를 사용해서 출력을 생성할 수 있다.

```python
>>> print(1 + 1)
# 2

>>> print("Hello\nWorld")
# Hello
# World
```

[코드 실행 확인](https://code.sololearn.com/285/#py)

<br>

> When a string is printed, the quotes around it are not displayed.
>
> 문자열이 출력되면, 따옴표가 표시되지 않는다.

<br>

<br>

## Input

###### 입력

<br>

- To get input from the user in Python, you can use the intuitively named `input` function.
  - 사용자로부터 입력을 받으려면, 명명된 `input` 함수를 사용할 수 있다.
- The function prompts the user for input, and returns what they enter as a string (with the contents automatically escaped).
  - 이 함수는 사용자에게 입력을 요구하고, 입력한 내용을 문자열로 반환한다.
  - (내용이 자동으로 이스케이프 된다)

```python
>>> input("Enter something please: ")
# Enter something please: 입력한 내용
```

[코드 실행 확인](https://code.sololearn.com/945/#py)

<br>

> The `print` and `input` functions aren't very useful at the Python console, which automatically does input and output.
>
> `print`와 `input` 함수는, 자동으로 입력과 출력을 수행하는 Python 콘솔에서 별로 유용하지 않다.
>
> However, they are very useful in actual programs.
>
> 하지만 실제 프로그램에서는 매우 유용하다.

<br>

<br>

#### QUIZ

- What is the output of this code?
  - 아래 코드의 출력은 무엇인가?

```python
>>> print('print("print")')
```

> `print("print")`

<br>

- Fill in the blank to prompt for user input.
  - 사용자의 입력을 요구해라.

```python
>>> input("Enter a number: ")
```

<br>

<br>