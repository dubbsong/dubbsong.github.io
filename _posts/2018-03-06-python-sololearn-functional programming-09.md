---
layout: post
title: "SoloLearn 번역 - 09. Module 6 Quiz (Functional Programming)"
categories: dev
tags: python
---

## QUIZ

- What is the result of this code?

```python
nums = {1, 2, 3, 4, 5, 6}
nums = {0, 1, 2, 3} & nums
nums = filter(lambda x: x > 1, nums)
print(len(list(nums)))


2
```

<br>

- What is the result of this code?

```python
def power(x, y):
   if y == 0:
      return 1
   else:
      return x * power(x, y - 1)
   
print(power(2, 3))


8
```

<br>

- Fill in the blanks to calculate the expression x*(x+1) using an anonymous function and call it for the number 6.

```python
a = (lambda x: x * (x + 1)) (6)
print(a)
```

<br>

- Fill in the blanks to leave only even numbers in the list.

```python
nums = [1, 2, 8, 3, 7]
res = list(filter(lambda x: x%2 == 0, nums))
print(res)
```

<br>

- Drag and drop from the options below to print only the items in the set "a" that are not in the set "b".

```python
print(a - b)
```

<br>