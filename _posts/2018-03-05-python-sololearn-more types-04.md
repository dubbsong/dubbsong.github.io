---
layout: post
title: "SoloLearn 번역 - 04. Tuples (More Types)"
categories: dev
tags: python
---

## Tuples

- **Tuples** are very similar to lists, except that they are immutable (they cannot be changed).
  - **Tuples**는 immutable을 제외하고는, 배열과 매우 비슷하다(변경할 수 없다).
- Also, they are created using **parentheses**, rather than square brackets.
  - 또한, 대괄호 대신 **괄호**를 사용해서 생성된다.

<br>

- Example:

```python
words = ("spam", "eggs", "sausages",)
```

<br>

- You can access the values in the tuple with their index, just as you did with lists:
  - 배열과 마찬가지로, 인덱스를 사용해서 tuple의 값에 엑세스 할 수 있다.

```python
print(words[0])
```

<br>

- Trying to reassign a value in a tuple causes a TypeError.
  - tuple의 값을 재할당하려고 하면 TypeError가 발생한다.

```python
words[1] = "cheese"
```

<br>

- Result:

```python
>>>
TypeError: 'tuple' object does not support item assignment
>>>
```

<br>

> Like lists and dictionaries, tuples can be nested within each other.
>
> 배열 및 dictionaries와 마찬가지로, tuple은 서로의 내부에 중접될 수 있다.

------

<br>

## Tuples 02

- Tuples can be created without the parentheses, by just separating the values with commas.
  - Tuple은 콤마로 값을 분리해서, 괄호 없이 생성될 수 있다.

<br>

- Example:

```python
my_tuple = "one", "two", "three"
print(my_tuple[0])
```

<br>

- Result:

```python
>>>
one
>>>
```

<br>

- An empty tuple is created using an empty parenthesis pair.
  - 빈 한 쌍의 괄호를 사용해서 빈 tuple이 생성된다.

```python
tpl = ()
```

<br>

> Tuples are faster than lists, but they cannot be changed.
>
> Tuple은 배열보다 빠르지만, 변경할 수 없다.

------

<br>

## QUIZ

- Fill in the blanks to create a list, dictionary, and tuple:

```python
# list
list = ["one", "two"]

# dictionary
dict = {1: "one", 2: "two"}

# tuple
tp = ("one", "two")
```

<br>

- What is the result of this code?
  - ((1, 2, 3))
  - 1
  - **(1, 2, 3)**

```python
tuple = (1, (1, 2, 3))
print(tuple[1])
```

<br>