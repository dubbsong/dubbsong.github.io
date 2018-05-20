---
layout: post
title: "SoloLearn 번역 - 02. Dictionaries (More Types)"
categories: dev
tags: python
---

## Dictionaries

- **Dictionaries** are data structures used to map arbitrary keys to values.
  - **Dictionaries**는 임의의 key를 값에 매핑하는 데 사용되는 데이터 구조이다.
- Lists can be thought of as dictionaries with integer keys within a certain range.
  - 배열은 특정 범위 내의 정수 key를 사용하는 dictionaries로 생각할 수 있다.
- Dictionaries can be indexed in the same way as lists, using **square brackets** containing keys.
  - Dictionaries는 key를 포함하는 **대괄호**를 사용해서 배열과 같은 방법으로 인덱스화 될 수 있다.

<br>

- Example:

```python
ages = {"Dave": 24, "Mary": 42, "John": 58}
print(ages["Dave"])
print(ages["Mary"])
```

<br>

- Result:

```python
>>>
24
42
>>>
```

<br>

- Each element in a dictionary is represented by a **key:value** pair.
  - dictionary의 각 요소는 **key:value** 쌍으로 표시된다.

------

<br>

## Dictionaries 02

- Trying to index a key that isn't part of the dictionary returns a **KeyError**.
  - dictionary의 일부가 아닌 key를 인덱스하려고 하면 **KeyError**가 반환된다.

<br>

- Example:

```python
primary = {
   "red": [255, 0, 0],
   "green": [0, 255, 0],
   "blue": [0, 0, 255],
}

print(primary["red"])
print(primary["yellow"])
```

<br>

- Result:

```python
>>>
[255, 0, 0]

KeyError: 'yellow'
>>>
```

<br>

- As you can see, a dictionary can store any types of data as values.
  - 보다시피, dictionary는 모든 타입의 데이터를 값으로 저장할 수 있다.

<br>

> An empty dictionary is defined as {}.
>
> 빈 dictionary는 {}로 정의된다.

------

<br>

## Dictionaries 03

- Only immutable objects can be used as keys to dictionaries.
  - immutable 객체만 dictionaries에 대한 key로 사용될 수 있다.
  - `immutable`: cannot be changed after it's created
- **Immutable** objects are those that can't be changed.
  - **Immutable** 객체는 변경할 수 없는 객체이다.
- So far, the only mutable objects you've come across are **lists** and **dictionaries**.
  - 지금까지, 변경 가능한 유일한 객체는 **배열**과 **dictionaries**이다.
- Trying to use a mutable object as a dictionary key causes a **TypeError**.
  - 변경 가능한 객체를 dictionary key로 사용하려고 하면 **TypeError**가 발생한다.

```python
bad_dict = {
   [1, 2, 3]: "one two three",
}
```

<br>

- Result:

```python
>>>
TypeError: unhashable type: 'list'
>>>
```

------

<br>

## QUIZ

- Fill in the blanks to define a valid dictionary with two elements.

```python
cars = {"BMW": "blue", "Volvo": "red"}
```

<br>

- What is the result of this code?
  - 0
  - None
  - **KeyError**

```python
test = {}
print(test[0])
```

<br>

- Which of these values can't be used as a dictionary key?
  - "one two three"
  - False
  - **{2: 4, 3: 9, 4: 16,}**

<br>