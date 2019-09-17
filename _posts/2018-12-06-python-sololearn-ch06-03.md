---
layout: post
title: "(Functional Programming 03) map & filter 함수"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

## map

- The built-in functions `map` and `filter` are very useful higher\-order functions that operate on lists (or similar objects called `iterables`).
  - 내장 함수 `map`과 `filter`는 아주 유용한 고차 함수이다.
  - 이 함수들은 리스트(또는 `iterables`라는 유사 객체)에서 작동한다.
- The function `map` takes a function and an iterable as arguments, and returns a new iterable with the function applied to each argument.
  - `map` 함수는 함수와 iterable을 인수로 사용해서, 각 인수에 적용된 함수로 새로운 iterable을 반환한다.

```python
def add_five(x):
  return x + 5

nums = [11, 22, 33, 44, 55]
result = list(map(add_five, nums))

print(result)
# [16, 27, 38, 49, 60]
```

[코드 실행 확인](https://code.sololearn.com/385/#py)

<br>

- We could have achieved the same result more easily by using `lambda` syntax.
  - `람다` 구문을 사용하면 동일한 결과를 더 쉽게 얻을 수 있었다.

```python
nums = [11, 22, 33, 44, 55]
result = list(map(lambda x: x+5, nums))

print(result)
# [16, 27, 38, 49, 60]
```

[코드 실행 확인](https://code.sololearn.com/386/#py)

<br>

> To convert the result into a list, we used `list` explicitly.
>
> 결과를 리스트로 변환하기 위해, `list`를 명시적으로 사용했다.

<br>

## filter

- The function `filter` filters an iterable by removing items that don't match a predicate (a function that returns a Boolean).
  - `filter` 함수는 predicate(불리언을 반환하는 함수)와 일치하지 않는 item을 제거해서 iterable을 필터링한다.

```python
nums = [11, 22, 33, 44, 55]
res = list(filter(lambda x: x%2 == 0, nums))

print(res)
# [22, 44]
```

[코드 실행 확인](https://code.sololearn.com/387/#py)

<br>

> Like `map`, the result has to be explicitly converted to a list if you want to print it.
>
> `map`과 같이, 결과가 명시적으로 변환되어야 한다.

<br>

<br>

#### QUIZ

- Fill in the blanks to multiply each item in the list by 2 using lambda syntax.
  - 람다 구문을 사용해서 리스트의 각 item에 2를 곱해라.

```python
nums = [11, 22, 33]
a = list(map(lambda x: x*2, nums))
```

<br>

- Fill in the blanks to extract all items that are less than 5 from the list.
  - 리스트에서 5보다 작은 모든 item을 추출해라.

```python
nums = [1, 2, 5, 8, 3, 0, 7]
res = list(filter(lambda x: x < 5, nums))

print(res)
```

<br>

<br>