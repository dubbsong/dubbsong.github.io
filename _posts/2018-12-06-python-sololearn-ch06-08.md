---
layout: post
title: "(Functional Programming 08) itertools 모듈"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- The module `itertools` is a standard library that contains several functions that are useful in functional programming.
  - `itertools` 모듈은, 함수형 프로그래밍에서 유용한 여러 함수를 포함하는 표준 라이브러리이다.
- One type of function it produces is infinite iterators.
  - 생성하는 함수 중 하나는, 무한 iterator(반복자)이다.
- The function `count` counts up infinitely from a value.
  - `count` 함수는 값을 무한 카운트한다.
- The function `cycle` infinitely iterates through an iterable (for instance a list or string).
  - `cycle` 함수는 iterable을 통해 무한 반복한다.
  - (예: 리스트 또는 문자열)
- The function `repeat` repeats an object, either infinitely or a specific number of times.
  - `repeat` 함수는 객체를 무한히 또는 특정 횟수만큼 반복한다.

```python
from itertools import count

for i in count(3):
  print(i)
  
  if i >= 11:
    break
    
# 3
# 4
# 5
# 6
# 7
# 8
# 9
# 10
# 11
```

[코드 실행 확인](https://code.sololearn.com/401/#py)

<br>

- There are many functions in `itertools` that operate on iterables, in a similar way to `map` and `filter`.
  - `itertools`에는 iterable에서 동작하는 많은 함수가 있다.
  - `map` 및 `filter`와 비슷한 방식이다.

- Some examples:
  - 몇 가지 예는 다음과 같다.

<br>

1. `takewhile`: takes items from an iterable while a predicate function remains true;
   - predicate 함수가 true인 동안, iterable에서 item을 가져온다.
2. `chain`: combines several iterables into one long one;
   - 여러 iterable을 긴 하나로 결합한다.
3. `accumulate`: returns a running total of values in an iterable.
   - iterable의 누적 총계 값을 반환한다.

```python
from itertools import accumulate, takewhile

nums = list(accumulate(range(8)))

print(nums)
# [0, 1, 3, 6, 10, 15, 21, 28]

print(list(takewhile(lambda x: x <= 6, nums)))
# [0, 1, 3, 6]
```

[코드 실행 확인](https://code.sololearn.com/402/#py)

<br>

- There are also several combinatoric functions in `itertool`, such as `product` and `permutation`.
  - `itertool`에는 `product` 및 `permutation`과 같은 몇 가지 조합 함수도 있다.
- These are used when you want to accomplish a task with all possible combinations of some items.
  - 일부 가능한 모든 item 조합으로 작업을 수행하려고 할 때 사용된다.

```python
from itertools import product, permutations

letters = ("A", "B")

print(list(product(letters, range(2))))
# [('A', 0), ('A', 1), ('B', 0), ('B', 1)]

print(list(permutations(letters)))
# [('A', 'B'), ('B', 'A')]
```

[코드 실행 확인](https://code.sololearn.com/403/#py)

<br>

<br>

#### QUIZ

- Fill in the blanks to import the cycle function from the itertools module.
  - itertools 모듈의 cycle 함수를 import 해라.

```python
from itertools import cycle
```

<br>

- Fill in the blanks to take the numbers from the list while they are even, using the takewhile function.
  - takewhile 함수를 사용해서, 짝수인 동안 리스트에서 숫자를 가져와라.

```python
from itertools import takewhile

nums = [2, 4, 6, 7, 9, 8]
a = takewhile(lambda x: x % 2 == 0, nums)

print(list(a))
```

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
from itertools import product

a = {1, 2}

print(len(list(product(range(3), a))))
```

> `6`

<br>

<br>