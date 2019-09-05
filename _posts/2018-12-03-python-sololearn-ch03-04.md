---
layout: post
title: "(Functions & Modules 04) 함수의 반환"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- Certain functions, such as `int` or `str`, return a value that can be used later.
  - 특정 함수는 나중에 사용될 수 있는 값을 반환한다.
- To do this for your defined functions, you can use the `return` statement.
  - 정의된 함수에 대해 이를 수행하기 위해, `return` 문을 사용할 수 있다.

```python
def max(x, y):
  if x >= y:
    return x
  else:
    return y
  
print(max(4, 7))
# 7

z = max(8, 5)
print(z)
# 8
```

[코드 실행 확인](https://code.sololearn.com/334/#py)

<br>

> The `return` statement cannot be used outside of a function definition.
>
> `return` 문은 함수 정의의 외부에서 사용할 수 없다.

<br>

- Once you return a value from a function, it immediately stops being executed.
  - 함수에서 값을 반환하면, 즉시 실행이 멈춘다.
- Any code after the `return` statement will never happen.
  - `return` 문 이후의 코드는 절대 실행되지 않는다.

```python
def add_numbers(x, y):
  total = x + y
  return total
  print("This won't be printed")
  
print(add_numbers(4, 5))
# 9
```

[코드 실행 확인](https://code.sololearn.com/335/#py)

<br>

<br>

#### QUIZ

- Fill in the blanks to define a function that compares the lengths of its arguments and returns the shortest one.
  - 인수의 길이를 비교하고, 가장 짧은 인수를 반환하는 함수를 정의해라.

```python
def shortest_string(x, y):
  if len(x) <= len(y):
    return x
  else:
    return y
```

<br>

- What is the highest number this function prints if called?
  - 이 함수가 호출된다면, 가장 높은 숫자는 무엇인가?

```python
def print_numbers():
  print(1)
  print(2)
  return
  print(4)
  print(6)
```

> `2`

<br>

<br>