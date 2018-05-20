---
layout: post
title: "SoloLearn 번역 - 01. None (More Types)"
categories: dev
tags: python
---

## None (None 객체)

- The **None** object is used to represent the absence of a value.
  - **None** 객체는 값의 부재를 나타내는 데 사용된다.
  - `None`: the absence of a value
- It is similar to **null** in other programming languages.
  - 다른 프로그래밍 언어의 **null**과 비슷하다.
- Like other "empty" values, such as 0, [] and the empty string, it is **False** when converted to a Boolean variable.
  - 0, [], 빈 문자열과 같은 다른 "빈" 값처럼, Boolean 변수로 변환하면 **False**이다.
- When entered at the Python console, it is displayed as the empty string.
  - Python 콘솔에서 입력하면, 빈 문자열로 표시된다.

```python
>>> None == None
True

>>> None
>>> print(None)
None
>>>
```

------

<br>

## None 02

- The None object is returned by any function that doesn't explicitly return anything else.
  - None 객체는 명시적으로 다른 것을 반환하지 않는 함수에 의해 반환된다.

```python
def some_func():
   print("Hi!")
   
var = some_func()
print(var)
```

<br>

- Result:

```python
>>>
Hi!
None
>>>
```

------

<br>

## QUIZ

- What is "None" often used to represent?
  - An invalid value
  - A false value
  - **Absence of a value**

<br>

- What number does this code print?

```python
foo = print()
if foo == None:
   print(1)
else:
   print(2)
   
   
1
```

<br>