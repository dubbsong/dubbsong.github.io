---
layout: post
title: "(More Type 08) 유용한 함수들"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- Python contains many useful built\-in functions and methods to accomplish common tasks.
  - Python에는 유용한 내장 함수와 메소드가 많이 있다.

<br>

- `join`: joins a list of strings with another string as a separator.
  - 문자열 리스트를 다른 문자열과 구분 기호로 결합한다.
- `replace`: replaces one substring in a string with another.
  - 문자열의 하위 문자열을 다른 것으로 대체한다.
- `startswith` and `endswith`: determine if there is a substring at the start and end of a string, respectively.
  - 문자열의 시작과 끝에 각각 하위 문자열이 있는지 확인한다.

<br>

- To change the case of a string, you can use `lower` and `upper`.
  - 문자열의 대소문자를 변경하기 위해 `lower`와 `upper`를 사용할 수 있다.
- The method `split` is the opposite of `join`, turning a string with a certain separator into a list.
  - `split` 메소드는 `join`과 반대이다.
  - 특정 구분 기호가 있는 문자열을 리스트로 변경한다.

<br>

- Some examples:

```python
print(",".join(["spam", "eggs", "ham"]))
# spam, eggs, ham

print("Hello ME".replace("ME", "World"))
# Hello World

print("This is a sentence.".startswith("This"))
# True

print("This is a sentence.".endswith("sentence."))
# True

print("This is a sentence.".upper())
# THIS IS A SENTENCE.

print("AN ALL CAPS SENTENCE".lower())
# an all caps sentence

print("spam, eggs, ham".split(","))
# ['spam', 'eggs', 'ham']
```

[코드 실행 확인](https://code.sololearn.com/377/#py)

<br>

## Numeric Functions

###### 숫자 함수

- To find the maximum or minimum of some numbers or a list, you can use `max` or `min`.
  - 일부 숫자 또는 리스트의 최대값 또는 최소값을 찾기 위해, `max` 또는 `min`을 사용할 수 있다.
- To find the distance of a number from zero (its absolute value), use `abs`.
  - 0으로부터의 거리(절대값)를 구하기 위해,  `abs`을 사용한다.
- To round a number to a certain number of decimal places, use `round`.
  - 특정 소수점 이하의 자릿수로 숫자를 반올림하기 위해, `round`를 사용한다.
- To find the total of a list, use `sum`.
  - 리스트의 총합을 구하기 위해,  `sum`을 사용한다.

```python
print(min(1, 2, 3, 4, 0, 2, 1))
# 0

print(max([1, 4, 9, 2, 5, 6, 8]))
# 9

print(abs(-99))
# 99

print(abs(42))
# 42

print(sum([1, 2, 3, 4, 5]))
# 15
```

[코드 실행 확인](https://code.sololearn.com/378/#py)

<br>

## List Functions

###### 리스트 함수

- Often used in conditional statements, `all` and `any` take a list as an argument, and return `True` if all or any (respectively) of their arguments evaluate to `True` (and `False` otherwise).
  - `all`과 `any`는 리스트를 인수로 사용하고, 종종 조건문에서 사용된다.
  - 인수가 `True`로 평가되면 `True`를 반환하고, 그렇지 않으면 `False`를 반환한다.
- The function `enumerate` can be used to iterate through the values and indices of a list simultaneously.
  - `enumerate` 함수는 리스트의 값과 색인을 동시에 반복하는 데 사용될 수 있다.

```python
nums = [55, 44, 33, 22, 11]

if all([i > 5 for i in nums]):
  print("All larger than 5")
  
if any([i % 2 == 0 for i in nums]):
  print("At least one is even")
  
for v in enumerate(nums):
  print(v)

# All larger than 5
# At least one is even
# (0, 55)
# (1, 44)
# (2, 33)
# (3, 22)
# (4, 11)
```

[코드 실행 확인](https://code.sololearn.com/379/#py)

<br>

<br>

#### QUIZ

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
a = min([sum([11, 22]), max(abs(-30), 2)])

print(a)
```

> `30`

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
nums = [-1, 2, -3, 4, -5]

if all([abs(i) < 3 for i in nums]):
  print(1)
else:
  print(2)
```

> `2`

<br>

<br>