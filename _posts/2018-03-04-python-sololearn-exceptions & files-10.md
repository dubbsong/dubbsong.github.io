---
layout: post
title: "SoloLearn 번역 - 10. Module 4 Quiz (Exceptions & Files)"
categories: dev
tags: python
---

## QUIZ

- Which number is not printed by this code?
  - **2**
  - 3
  - 4

```python
try:
   print(1)
   print(20 / 0)
   print(2)
except ZeroDivisionError:
   print(3)
finally:
   print(4)
```

<br>

- Open the file in binary write mode.

```python
open("text.txt", "wb")
```

<br>

- Fill in the blanks to try to open and read from a file. Print an error message in case of an exception.

```python
try:
   with open("text.txt") as f:
	print(f.read())
except:
   print("Error")
```

<br>

- What is the highest number that would be printed by this code?

```python
try:
   print(1)
   assert 2 + 2 == 5
except AssertionError:
   print(3)
except:
   print(4)
   

3
```

<br>