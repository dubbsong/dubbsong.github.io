---
layout: post
title: "SoloLearn - 04. Returning from Functions (Function & Modules)"
categories: dev
tags: python
---

## Returning from Functions (함수에서 반환하기)

- Certain functions, such as **int** or **str**, return a value that can be used later.
  - **int** 또는 **str**과 같은 특정 함수는 나중에 사용할 수 있는 값을 반환한다.
- To do this for your defined functions, you can use the **return** statement.
  - 정의된 함수에 이렇게 하려면, **return** 문을 사용할 수 있다.

<br>

- For example:

```python
def max(x, y):
   if x >= y:
      return x
   else:
      return y
   
print(max(4, 7))
z = max(8, 5)
print(z)
```

<br>

- Result:

```python
>>>
7
8
>>>
```

<br>

> The **return** statement cannot be used outside of a function definition.
>
> **return** 문은 함수 정의 외부에서 사용할 수 없다.

<br>

## Returning from Functions 02

- Once you return a value from a function, it immediately stops being executed.
  - 함수에서 값을 반환하면, 즉시 실행이 멈춘다.
- Any code after the **return** statement will never happen.
  - **return** 문 다음의 코드는 절대 발생하지 않는다.

<br>

- For example:

```python
def add_numbers(x, y):
   total = x + y
   return total
	print("This won't be printed")
   
print(add_numbers(4, 5))
```

<br>

- Result:

```python
>>>
9
>>>
```

<br>

## QUIZ

- Fill in the blanks to define a function that compares the lengths of its arguments and returns the shortest one.

```python
def shortest_string(x, y):
   if len(x) <= len(y):
      return x
   else:
      return y
```

<br>

- What is the highest number this function prints if called?

```python
def print_numbers():
   print(1)
   print(2)
   return
	print(4)
   print(6)
   
2
```

<br>