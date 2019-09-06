---
layout: post
title: "(Functions & Modules 09) QUIZ"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- Fill in the blanks to define a function that takes two numbers as arguments and returns the smaller one.
  - 두 개의 숫자를 인수로 사용하고, 더 작은 숫자를 반환하는 함수를 정의해라.

```python
def min(x, y):
  if x <= y:
    return x
  else:
    return y
```

<br>

- Rearrange the code to define a function that calculates the sum of all numbers from 0 to its argument.
  - 0부터 인수까지 모든 숫자의 합을 계산하는 함수를 정의해라.

```python
def sum(x):
  res = 0
  
  for i in range(x):
    res += i
    return res
```

<br>

- How would you refer to the randint function if it was imported like this?
  - randint 함수를 다음과 같이 import하면, 어떻게 참조해야 하는가?

```python
from random import randint as rnd_int
```

> `rnd_int`

<br>

- What is the highest number output by this code?
  - 이 코드에서 가장 큰 수의 출력은 무엇인가?

```python
def print_nums(x):
  for i in range(x):
    print(i)
    return
  
print_nums(10)
```

> `0`

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
def func(x):
  res = 0
  
  for i in range(x):
    res += i
    return res
  
print(func(4))
```

> `6`

<br>

<br>