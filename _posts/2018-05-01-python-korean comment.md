---
layout: post
title: "Python 파일에서 한글 주석 사용하는 방법"
categories: dev
tags: python
---

## Python 파일에서 한글 주석 사용하기

- Python 파일 최상단에 `# -*- coding: utf-8 -*-`을 입력하면 한글 주석을 사용할 수 있다.

<br>

#### Example 01: summation.py

```python
def summation(n):
   return sum(range(1, n + 1))

# sum() 메소드
# 반복 가능한 항목을 추가하고, 합을 반환한다.


summation(10)	# 55

SyntaxError: Non-ASCII character
```

<br>

#### Example 02:

```python
# -*- coding: utf-8 -*-

def summation(n):
   return sum(range(1, n + 1))

# sum() 메소드
# 반복 가능한 항목을 추가하고, 합을 반환한다.


summation(10)	# 55

55
```

<br>