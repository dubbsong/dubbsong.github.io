---
layout: post
title: "SoloLearn 번역 - 02. Functions (Function & Modules)"
categories: dev
tags: python
---

## Functions (함수)

- In addition to using pre-defined functions, you can create your own functions by using the **def** statement.
  - 미리 정의된 함수를 사용하는 것뿐만 아니라, **def** 문을 사용해서 고유한 함수를 만들 수 있다.
  - `def`: defines a function or method
- Here is an example of a **function** named **my-func**.
  - 다음은 **my-func**이라는 **함수**의 예이다.
  - `function`: a parameterized sequence of statements
- It takes no arguments, and prints "spam" three times.
  - 인수를 취하지 않고, "spam"을 세 번 출력한다.
- It is defined, and then called.
  - 정의하고, 그 다음 호출된다.
- The statements in the function are executed only when the function is called.
  - 함수 안의 명령문은 함수가 호출될 때만 실행된다.

```python
def my_func():
   print("spam")
   print("spam")
   print("spam")
   
my_func()
```

<br>

- Result:

```python
>>>
spam
spam
spam
>>>
```

<br>

> The code block within every function starts with a colon (:) and is **indented**.
>
> 모든 함수 내의 코드 블록은 콜론 (:)으로 시작되고 들여쓰기 된다.

------

<br>

## Functions 02

- You must define functions before they are called, in the same way that you must assign variables before using them.
  - 변수를 사용하기 전에 변수를 할당해야 하는 것처럼, 함수를 호출하기 전에 함수를 정의해야 한다.

```python
hello()

def hello():
   print("Hello world!")
```

<br>

- Result:

```python
>>>
NameError: name 'hello' is not defined
```

------

<br>

## QUIZ

- Fill in the blanks to define a function named hello:

```python
def hello():
   print("Hi!")
```

<br>

- Rearrange the code to declare a function sayHi() and call it.
  1. def sayHi():
  2. print("Hi!")
  3. sayHi()

<br>