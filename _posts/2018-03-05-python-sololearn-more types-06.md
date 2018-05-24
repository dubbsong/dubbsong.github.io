---
layout: post
title: "SoloLearn 번역 - 06. List Comprehensions (More Types)"
categories: dev
tags: python
---

## List Comprehensions

- **List comprehensions** are a useful way of quickly creating lists whose contents obey a simple rule.
  - **List comprehensions**는 규칙을 따르는 내용이 간단한 배열을 빠르게 만드는 유용한 방법이다.
- For example, we can do the following:
  - 예를 들어, 다음과 같이 할 수 있다.

```python
# a list comprehension
cubes = [i**3 for i in range(5)]

print(cubes)
```

<br>

- Result:

```python
>>>
[0, 1, 8, 27, 64]
```

<br>

> List comprehensions are inspired by set-builder notation in mathematics.
>
> List comprehensions는 수학의 set-builder 표기법에서 영감을 얻었다.

------

<br>

## List Comprehensions 02

- A list comprehension can also contain an if statement to enforce a condition on values in the list.
  - list comprehension은 조건을 적용하는 if문이 포함될 수 있다.

<br>

- Example:

```python
evens = [i**2 for i in range(10) if i**2 % 2 == 0]
print(evens)
```

<br>

- Result:

```python
>>>
[0, 4, 16, 36, 64]
>>>
```

------

<br>

## List Comprehensions 03

- Trying to create a list in a very extensive range will result in a **MemoryError**.
  - 매우 광범위한 범위에서 배열을 만들려고 하면 **MemoryError**가 발생한다.
- This code shows an example where the list comprehension runs out of memory.
  - 아래 예제 코드는 list comprehension이 부족한 경우를 보여준다.

```python
even = [2*i for i in range(10**100)]
```

<br>

- Result:

```python
>>>
MemoryError
>>>
```

<br>

> This issue is solved by **generators**, which are covered in the next module.
>
> 이 문제는 다음 모듈에서 다루는 generators로 해결된다.

------

<br>

## QUIZ

- What does this list comprehension create?
  - A list of all numbers between 0 and 10
  - A list of even numbers between 0 and 10
  - **A list of even numbers between 0 and 18**

```python
nums = [i*2 for i in range(10)]
```

<br>

- Create a list of multiples of 3 from 0 to 20.

```python
a = [i for i in range(20) if i % 3 == 0]
```

<br>

- Fill in the blanks to create a list of numbers multiplied by 10 in the range of 5 to 9.

```python
a = [x*10 for x in range(5, 9)]
```

<br>