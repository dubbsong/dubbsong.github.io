---
layout: post
title: "SoloLearn - 09. Module 3 Quiz (Function & Module)"
categories: dev
tags: python
---

## QUIZ

- Fill in the blanks to define a function that takes two numbers as arguments and returns the smaller one.

```python
def min(x, y):
   if x <= y:
      return x
   else:
      return y
```

<br>

- Rearrange the code to define a function that calculates the sum of all numbers from 0 to its argument.

```python
def sum(x):
   res = 0
   for i in range(x):
      res += i
	return res
```

<br>

- How would you refer to the randint function if it was imported like this?
  - randint
  - random.rnd_int
  - **rnd_int**

```python
from random import randint as rnd_int
```

<br>

- What is the highest number output by this code?

```python
def print_nums(x):
   for i in range(x):
      print(i)
      return
   print_nums(10)
   
0
```

<br>

- What is the output of this code?

```python
def func(x):
   res = 0
   for i in range(x):
      res += i
	return res

print(func(4))


6
```

<br>