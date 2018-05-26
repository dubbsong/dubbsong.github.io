---
layout: post
title: "SoloLearn 번역 - 03. map (Functional Programming)"
categories: dev
tags: python
---

## map

- The built-in functions **map** and **filter** are very useful higher-order functions that operate on lists (or similar objects called **iterables**).
  - 내장된 함수 **map**과 **filter**는 배열(또는 **iterables**라는 유사 객체)에서 작동하는 매우 유용한 고차 함수이다.
  - `iterable`: a container object capable of returning its members one at a time (한 번에 하나씩 그 멤버를 반환할 수 있는 컨테이너 객체)
- The function **map** takes a function and an iterable as arguments, and returns a new iterable with the function applied to each argument.
  - 함수 **map**은 함수 및 iterable을 인수로 취해서, 각 인수에 적용된 함수로 새로운 iterable을 반환한다.

<br>

- Example:

```python
def add_five(x):
   return x + 5

nums = [11, 22, 33, 44, 55]
result = list(map(add_five, nums))
print(result)
```

<br>

- Result:

```python
>>>
[16, 27, 38, 49, 60]
>>>
```

<br>

- We could have achieved the same result more easily by using lambda syntax.
  - 람다 문법을 사용하면 더 쉽게 동일한 결과를 얻을 수 있었다.

```python
nums = [11, 22, 33, 44, 55]

result = list(map(lambda x: x+5, nums))
print(result)
```

<br>

> To convert the result into a list, we used **list** explicitly.
>
> 결과를 배열로 변환하기 위해, **배열**을 명시적으로 사용했다.

------

<br>

## filter

- The function **filter** filters an iterable by removing items that don't match a predicate (a function that returns a Boolean).
  - 함수 **filter**는 술어(불리언을 반환하는 함수)와 일치하지 않는 항목을 제거해서 iterable을 필터링한다.

<br>

- Example:

```python
nums = [11, 22, 33, 44, 55]
res = list(filter(lambda x: x%2==0, nums))
print(res)
```

<br>

- Result:

```python
>>>
[22, 44]
>>>
```

<br>

> Like **map**, the result has to be explicitly converted to a list if you want to print it.
>
> **map**과 마찬가지로, 결과를 출력하려면 명시적으로 배열을 변환해야 한다.

------

<br>

## QUIZ

- Fill in the blanks to multiply each item in the list by 2 using lambda syntax.

```python
nums = [11, 22, 33]
a = list(map(lambda x: x*2, nums))
```

<br>

- Fill in the blanks to remove all items that are greater than 4 from the list.

```python
nums = [1, 2, 5, 8, 3, 0, 7]
res = list(filter(lambda x: x < 5, nums))
print(res)
```

<br>























































