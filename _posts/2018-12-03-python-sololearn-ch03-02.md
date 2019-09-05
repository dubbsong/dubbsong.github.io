---
layout: post
title: "(Functions & Modules 02) 함수"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- In addition to using pre-defined functions, you can create your own functions by using the `def` statement.
  - 미리 정의된 함수를 사용하는 것 외에도, `def` 문을 사용해서 고유한 함수를 작성할 수 있다.
- Here is an example of a function named `my_func`.
  - 다음은 `my_func`라는 함수의 예제이다.
- It takes no arguments, and prints "spam" three times.
  - 인수는 사용하지 않고, "spam"을 세 번 출력한다.
- The statements in the function are executed only when the function is called.
  - 함수의 명령문은 함수가 호출될 때에만 실행된다.

```python
def my_func():
  print("spam")
  print("spam")
  print("spam")
  
my_func()
```

[코드 실행 확인](https://code.sololearn.com/329/#py)

<br>

> The code block within every function starts with a colon (:) and is `indented`.
>
> 모든 함수 내의 코드 블록은 콜론(:)으로 시작되고, `들여쓰기` 된다.

<br>

- You must define functions before they are called, in the same way that you must assign variables before using them.
  - 변수를 사용하기 전에 변수를 할당하는 것과 같은 방식으로, 함수를 호출하기 전에 함수를 정의해야 한다.

```python
hello()

def hello():
  print("How are you?")
  
# NameError: name 'hello' is not defined
```

[코드 실행 확인](https://code.sololearn.com/330/#py)

<br>

<br>

#### QUIZ

- Fill in the blanks to define a function named hello:
  - hello라는 함수를 정의해라.

```python
def hello():
  print("How are you?")
```

<br>

- Rearrange the code to declare a function sayHi() and call it.
  - SayHi() 함수를 선언하고 호출해라.

```python
def sayHi():
  print("Hi!")
  
sayHi()
```

<br>

<br>