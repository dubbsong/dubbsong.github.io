---
layout: post
title: "(More Types 04) 튜플"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- `Tuples` are very similar to lists, except that they are immutable (they cannot be changed).
  - `튜플`은 변경 불가능(immutable)하다는 점을 제외하고는, 리스트와 매우 유사하다.
- Also, they are created using `parentheses`, rather than square brackets.
  - 대괄호 대신 `괄호`를 사용해서 생성한다.

```python
words = ("spam", "eggs", "sausages")
```

<br>

- You can access the values in the tuple with their index, just as you did with lists:
  - 리스트와 마찬가지로, 색인으로 튜플의 값에 액세스할 수 있다.

```python
print(words[0])
```

[코드 실행 확인](https://code.sololearn.com/365/#py)

<br>

- Trying to reassign a value in a tuple causes a TypeError.
  - 튜플에서 값을 재할당하려고 하면, TypeError가 발생한다.

```python
words[1] = "cheese"
# TypeError: 'tuple' object does not support item assignment
```

[코드 실행 확인](https://code.sololearn.com/366/#py)

<br>

> Like lists and dictionaries, tuples can be nested within each other.
>
> 리스트 및 딕셔너리처럼, 튜플은 서로 중첩될 수 있다.

<br>

- Tuples can be created without the parentheses, by just separating the values with commas.
  - 튜플은 괄호 없이 생성될 수 있다.
  - 값을 쉼표로 구분한다.

```python
my_tuple = "one", "two", "three"

print(my_tuple[0])
# one
```

[코드 실행 확인](https://code.sololearn.com/367/#py)

<br>

- An empty tuple is created using an empty parenthesis pair.
  - 빈 튜플은 빈 괄호 쌍을 사용해서 생성한다.

```python
tpl = ()
```

<br>

> Tuples are faster than lists, but they cannot be changed.
>
> 튜플은 리스트보다 빠르지만, 변경할 수 없다.

<br>

<br>

#### QUIZ

- Fill in the blanks to create a list, dictionary, and tuple:
  - 리스트, 딕셔너리, 튜플을 생성해라.

```python
# 리스트
list = ["one", "two"]

# 딕셔너리
dict = {1: "one", 2: "two"}

# 튜플
tp = ("one", "two")
```

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
tuple = (1, (1, 2, 3))
print(tuple[1])
```

> `(1, 2, 3)`

<br>

<br>