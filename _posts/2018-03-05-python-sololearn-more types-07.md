---
layout: post
title: "SoloLearn 번역 - 07. String Formatting (More Types)"
categories: dev
tags: python
---

## String Formatting (문자열 서식)

- So far, to combine strings and non-strings, you've converted the non-strings to strings and added them.
  - 지금까지, 문자열과 비 문자열을 결합하기 위해, 비 문자열을 문자열로 변환해서 추가했다.
- String formatting provides a more powerful way to embed non-strings within strings.
  - 문자열 서식은 문자열 내에 비 문자열을 포함시키는 더 강력한 방법을 제공한다.
- String formatting uses a string's **format** method to substitute a number of arguments in the string.
  - 문자열 서식은 문자열의 **서식** 메소드를 사용해서 문자열의 여러 인수를 대신한다.

<br>

- Example:

```python
# string formatting

nums = [4, 5, 6]
msg = "Numbers: {0} {1} {2}".format(nums[0], nums[1], nums[2])
print(msg)
```

<br>

- Result:

```python
>>>
Numbers: 4 5 6
>>>
```

<br>

> Each argument of the format function is placed in the string at the corresponding position, which is determined using the curly braces {}.
>
> format 함수의 각 인수는 중괄호 {}를 사용해서 결정되는 해당 위치의 문자열에 배치된다.

------

<br>

## String Formatting 02

- String formatting can also be done with named arguments.
  - 문자열 형식은 명명된 인수를 사용해서 수행할 수도 있다.

<br>

- Example:

```python
a = "{x}, {y}".format(x=5, y=12)
print(a)
```

<br>

- Result:

```python
>>>
5, 12
>>>
```

------

<br>

## QUIZ

- What is the result of this code?

```python
print("{0}{1}{0}".format("abra", "cad"))

abracadabra
```

<br>

- What is the result of this code?
  - 5, 9, 7
  - 9, 7, 5
  - **7, 9, 5**

```python
str="{c}, {b}, {a}".format(a=5, b=9, c=7)
print(str)
```

<br>