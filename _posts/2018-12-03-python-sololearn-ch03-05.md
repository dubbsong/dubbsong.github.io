---
layout: post
title: "(Functions & Modules 05) 주석 & 문서화 문자열(Docstrings)"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

## Comments

###### 주석

<br>

- `Comments` are annotations to code used to make it easier to understand.
  - `주석`은 코드를 이해하기 쉽도록 하는 데 사용된다.
- They don't affect how code is run.
  - 코드 실행에는 영향을 미치지 않는다.
- In Python, a comment is created by inserting an `octothorpe` (otherwise known as a number sign or hash symbol: \#).
  - Python의 주석은 `octothorpe (#)`를 삽입해서 생성한다.
- All text after it on that line is ignored.
  - \# 뒤의 모든 텍스트는 무시된다.

```python
x = 365
y = 7
# this is a comment

print(x % y)  # find the remainder
# 1
# print (x // y)
# another comment
```

[코드 실행 확인](https://code.sololearn.com/336/#py)

<br>

> Python doesn't have general purpose multiline comments, as do programming languages such as C.
>
> Python은 다중 행 주석을 가지고 있지 않다.

<br>

## Docstrings

###### 문서화 문자열

<br>

- `Docstrings` (documentation strings) serve a similar purpose to comments, as they are designed to explain code.
  - `Docstrings`는 코드를 설명하도록 설계되었으므로, 주석과 비슷한 용도로 사용된다.
- However, they are more specific and have a different syntax.
  - 하지만 더 구체적인 다른 문법을 가진다.
- They are created by putting a multiline string containing an explanation of the function below the `function's first line`.
  - `함수의 첫 번째 줄` 아래에 함수의 설명이 포함된 여러 줄 문자열을 넣어서 생성한다.

```python
def shout(word):
  """
  Print a word with an
  exclamation mark following it.
  """
  print(word + "!")
  
shout("spam")
# spam!
```

[코드 실행 확인](https://code.sololearn.com/337/#py)

<br>

> Unlike conventional comments, `docstrings` are retained throughout the runtime of the program.
>
> `docstrings`는 프로그램의 런타임 동안 유지된다.
>
> This allows the programmer to inspect these comments at runtime.
>
> 프로그래머는 런타임 중에 이러한 주석을 검사할 수 있다.

<br>

<br>

#### QUIZ

- Can a docstring contain multiple lines of text?
  - docstring에 여러 줄 텍스트를 포함시킬 수 있는가?

> `Yes`

<br>

<br>