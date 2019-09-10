---
layout: post
title: "(More Types 01) None 객체"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- The `None` object is used to represent the absence of a value.
  - `None` 객체는 값이 없음을 나타내는 데 사용된다.
- It is similar to `null` in other programming languages.
  - 다른 프로그래밍 언어의 `null`과 비슷하다.
- Like other "empty" values, such as 0, \[\] and the empty string, it is `False` when converted to a Boolean variable.
  - 다른 "빈" 값(0, \[\], 빈 문자열)과 마찬가지로, 불리언(Boolean) 변수로 변환하면 `False`이다.
- When entered at the Python console, it is displayed as the empty string.
  - Python 콘솔에서 입력하면, 빈 문자열로 표시된다.

```python
>>> None == None
# True

>>> print(None)
# None
```

[코드 실행 확인](https://code.sololearn.com/357/#py)

<br>

- The `None` object is returned by any function that doesn't explicitly return anything else.
  - `None` 객체는 명시적으로 다른 것을 반환하지 않는 함수에 의해 반환된다.

```python
def some_func():
  print("How are you?")
# How are you?
  
var = some_func()
print(var)
# None
```

[코드 실행 확인](https://code.sololearn.com/358/#py)

<br>

<br>

#### QUIZ

- What is "None" often used to represent?
  - "None"은 무엇을 나타내는가?

> Absence of a value
>
> 값이 없음을 나타낸다.

<br>

- What number does this code print?
  - 이 코드는 무슨 숫자를 출력하는가?

```python
foo = print()

if foo == None:
  print(1)
else:
  print(2)
```

> `1`

<br>

<br>