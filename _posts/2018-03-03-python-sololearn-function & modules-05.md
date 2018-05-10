---
layout: post
title: "SoloLearn - 05. Comments & Docstrings (Function & Modules)"
categories: dev
tags: python
---

## Comments (주석)

- **Comments** are annotations to code used to make it easier to understand.
  - **주석**은 이해하기 쉽게 하기 위해 사용되는 코드에 대한 주석이다.
- They don't affect how code is run.
  - 주석은 코드가 실행되는 방식에는 영향을 주지 않는다.
- In Python, a comment is created by inserting an **octothorpe** (otherwise known as a number sign or hash symbol: #).
  - Python에서 주석은 **#**을 삽입해서 작성된다.
- All text after it on that line is ignored.
  - 해당 행의 모든 텍스트는 무시된다.

<br>

- For example:

```python
x = 365
y = 7
# this is a comment

print(x % y) # find the remainder
# print (x // y)
# another comment
```

<br>

- Result:

```python
>>>
1
>>>
```

<br>

> Python doesn't have general purpose multiline comments, as do programming languages such as C.
>
> Python은 C와 같은 프로그래밍 언어처럼 일반적인 목적의 여러 행 주석을 가지고 있지 않다.

<br>

## Docstrings (한글로 어떻게?)

- **Docstrings** (documentation strings) serve a similar purpose to comments, as they are designed to explain code.
  - **Docstrings**(문서화 문자열)은 코드를 설명하기 위해 설계된 주석과 비슷한 용도로 사용된다.
- However, they are more specific and have a different syntax.
  - 하지만, 이것들은 보다 구체적이고 다른 문법을 사용한다.
- They are created by putting a multiline string containing an explanation of the function below the function's first line.
  - 함수의 첫 번째 행 아래에 함수에 대한 설명이 들어있는 여러 행 문자열을 입력해서 생성된다.

```python
def shout(word):
   """
   Print a word with an
   exclamation mark following it.
   """
   print(word + "!")
   
shout("spam")
```

<br>

- Result:

```python
>>>
spam!
>>>
```

<br>

> Unlike conventional comments, **docstrings** are retained throughout the runtime of the program.
>
> 일반적인 주석과는 달리, **docstrings**는 프로그램의 런타임 동안 유지된다.

> This allows the programmer to inspect these comments at run time.
>
> 이를 통해 프로그래머는 런타임에서 이러한 주석을 검사할 수 있다.

<br>

## QUIZ

- Fill in the blank to comment out the text:

```python
x = 8
	# printing x
   print(x)
```

<br>

- Can a docstring contain multiple lines of text?
  - No
  - **Yes**

<br>