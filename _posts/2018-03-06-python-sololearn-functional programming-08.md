---
layout: post
title: "SoloLearn 번역 - 08. itertools (Functional Programming)"
categories: dev
tags: python
---

## itertools

- The module **itertools** is a standard library that contains several functions that are useful in functional programming.
  - 모듈 **itertools**는 함수형 프로그래밍에 유용한 여러 함수를 포함하는 표준 라이브러리이다.
- One type of function it produces is infinite iterators.
  - 생성하는 함수의 한 타입은 무한 반복자이다.
- The function **count** counts up infinitely from a value.
  - **count** 함수는 값에서 무한대로 카운트한다.
- The function **cycle** infinitely iterates through an iterable (for instance a list or string).
  - **cycle** 함수는 iterable(예로, 배열 또는 문자열)을 통해 무한대로 반복한다.
- The function **repeat** repeats an object, either infinitely or a specific number of times.
  - **repeat** 함수는 객체를 무한히 반복하거나, 특정 횟수만큼 반복한다.

<br>

- Example:

```python
from itertools import count

for i in count(3):
   print(i)
   if i >= 11:
      break
```

<br>

- Result:

```python
>>>
3
4
5
6
7
8
9
10
11
>>>
```

------

<br>

## itertools 02

- There are many functions in **itertools** that operate on iterables, in a similar way to **map** and **filter**.
  - **itertools**에는 iterable에서 작동하는 많은 함수가 있다. 같은 방법으로 **map**과 **filter**가 있다.

<br>

#### Some Examples:

- **takewhile** - takes items from an iterable while a predicate function remains true;
  - **takewhile** - predicate 함수가 true인 동안 iterable의 항목을 취한다.
  - `predicate function`: a function that returns a Boolean
- **chain** - combines several iterables into one long one;
  - **chain** - 하나의 긴 iterable에 여러 개의 iterable을 결합한다.
- **accumulate** - returns a running total of values in an iterable.
  - **accumulate** - iterable에 누계(누적 합계) 값을 반환한다.

```python
from itertools import accumulate, takewhile

nums = list(accumulate(range(8)))
print(nums)
print(list(takewhile(lambda x: x <= 6, nums)))
```

<br>

- Result:

```python
>>>
[0, 1, 3, 6, 10, 15, 21, 28]
[0, 1, 3, 6]
>>>
```

------

<br>

## itertools 03

- There are also several combinatoric functions in **itertool**, such as **product** and **permutation**.
  - **itertool**에는 **product** 및 **permutation**과 같은 여러 조합 함수가 있다.
- These are used when you want to accomplish a task with all possible combinations of some items.
  - 일부 항목의 가능한 모든 조합으로 작업을 수행하려는 경우에 사용된다.

<br>

- Example:

```python
from itertools import product, permutations

letters = ("A", "B")
print(list(product(letters, range(2))))
print(permutations(letters))
```

<br>

- Result:

```python
>>>
[('A', 0), ('A', 1), ('B', 0), ('B', 1)]
[('A', 'B'), ('B', 'A')]
>>>
```

------

<br>

## QUIZ

- Fill in the blanks to import the cycle function from the itertools module.

```python
from itertools import cycle
```

<br>

- Fill in the blanks to take the numbers from the list while they are even, using the takewhile function.

```python
from itertools import takewhile
nums = [2, 4, 6, 7, 9, 8]
a = takewhile(lambda x: x%2==0, nums)
print(list(a))
```

<br>

- What is the output of this code?

```python
from itertools import product
a = {1, 2}
print(len(list(product(range(3), a))))


6
```

<br>