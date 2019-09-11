---
layout: post
title: "(More Type 06) 리스트 Comprehension"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- `List comprehensions` are a useful way of quickly creating lists whose contents obey a simple rule.
  - `리스트 comprehension`은 리스트를 빠르게 생성하는 유용한 방법이다.
  - 간단한 규칙을 따른다.

```python
cubes = [i**3 for i in range(5)]

print(cubes)
# [0, 1, 8, 27, 64]
```

[코드 실행 확인](https://code.sololearn.com/372/#py)

<br>

> List comprehensions are inspired by set-builder notation in mathematics.
>
> 리스트 comprehension은 수학의 set-builder 표기법에서 영감을 얻었다.

<br>

- A list comprehension can also contain an `if` statement to enforce a condition on values in the list.
  - 리스트 comprehension은 리스트의 값에 조건을 적용하기 위해 `if` 문을 포함할 수도 있다.

```python
evens = [i**2 for i in range(10) if i**2 % 2 == 0]

print(evens)
# [0, 4, 16, 36, 64]
```

[코드 실행 확인](https://code.sololearn.com/373/#py)

<br>

- Trying to create a list in a very extensive range will result in a `MemoryError`.
  - 아주 넓은 범위에서 리스트를 생성하려고 하면, `MemoryError`가 발생한다.
- This code shows an example where the list comprehension runs out of memory.
  - 아래 코드는 리스트 comprehension에 메모리가 부족한 예를 보여준다.

```python
even = [2*i for i in range(10**100)]

# MemoryError
```

[코드 실행 확인](https://code.sololearn.com/374/#py)

<br>

> This issue is solved by `generators`, which are covered in the next module.
>
> 이 이슈(issue)는, 다음 모듈에서 다루는 `생성기(generator)`로 해결된다.

<br>

<br>

#### QUIZ

- What does this list comprehension create?
  - 이 리스트 comprehension은 무엇을 생성하는가?

```python
nums = [i*2 for i in range(10)]
```

> A list of even numbers between 0 and 18
>
> 0과 18 사이의 짝수 리스트

<br>

- Create a list of multiples of 3 from 0 to 20.
  - 0부터 20까지 3의 배수 리스트를 생성해라.

```python
a = [i for i in range(20) if i % 3 == 0]
```

<br>

- Fill in the blanks to create a list of numbers multiplied by 10 in the range of 5 to 9.
  - 5에서 9까지의 숫자에 10을 곱한 숫자 리스트를 생성해라.

```python
a = [x*10 for x in range(5, 9)]
```

<br>

<br>