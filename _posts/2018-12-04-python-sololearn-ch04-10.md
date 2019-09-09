---
layout: post
title: "(Exception & Files 10) QUIZ"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- Which number is not printed by this code?
  - 어떤 숫자가 출력되지 않는가?

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

> `2`

<br>

- Open the file in binary write mode.
  - 2진 write mode로 파일을 열어라.

```python
open("text.txt", "wb")
```

<br>

- Fill in the blanks to try to open and read from a file.
  - 파일을 열고 읽어라.
- Print an error message in case of an exception.
  - 예외가 발생하면 에러 메시지를 출력해라.

```python
try:
  with open("text.txt") as f:
    print(f.read())
except:
  print("Error")
```

<br>

- What is the highest number that would be printed by this code?
  - 출력되는 가장 큰 숫자는 무엇인가?

```python
try:
  print(1)
  assert 2 + 2 == 5
except AssertionError:
  print(3)
except:
  print(4)
```

> `3`

<br>

<br>