---
layout: post
title: "(More Types 02) 딕셔너리"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- `Dictionaries` are data structures used to map arbitrary keys to values.
  - `딕셔너리`는 임의의 key를 값에 매핑하는 데 사용되는 데이터 구조(data structure)이다.
- Lists can be thought of as dictionaries with integer keys within a certain range.
  - 리스트는 특정 범위 내에서 정수 key가 있는 딕셔너리로 생각할 수 있다.
- Dictionaries can be indexed in the same way as lists, using `square brackets` containing keys.
  - 딕셔너리는 key를 포함하는 `대괄호`를 사용해서, 리스트와 같은 방식으로 색인화(indexed) 할 수 있다.

```python
ages = {"Sam": 27, "Ralph": 34, "Leo": 26}

print(ages["Sam"])
# 27

print(ages["Ralph"])
# 34

print(ages["Leo"])
# 26
```

[코드 실행 확인](https://code.sololearn.com/359/#py)

<br>

> Each element in a dictionary is represented by a `key:value` pair.
>
> 딕셔너리의 각 엘리먼트는 `key:value` 쌍으로 나타낸다.

<br>

- Trying to index a key that isn't part of the dictionary returns a `keyError`.
  - 딕셔너리의 일부가 아닌 key를 색인하려고 하면, `KeyError`가 반환된다.

```python
primary = {
  "red": [255, 0, 0],
  "green": [0, 255, 0],
  "blue": [0, 0, 255]
}

print(primary["red"])
# [255, 0, 0]

print(primary["yellow"])
# KeyError: 'yellow'
```

[코드 실행 확인](https://code.sololearn.com/360/#py)

<br>

> An empty dictionary is defined as `{}`.
>
> 빈 딕셔너리는 `{}`로 정의된다.

<br>

- Only `immutable` objects can be used as keys to dictionaries.
  - `Immutable(변경할 수 없는)` 객체만 딕셔너리에 key로 사용될 수 있다.
- `Immutable` objects are those that can't be changed.
  - `Immutable` 객체는 변경될 수 없는 객체이다.
- So far, the only mutable objects you've come across are `lists` and `dictionaries`.
  - 지금까지 접한 mutable(변경 가능한) 객체는 오직 `리스트`와 `딕셔너리`이다.
- Trying to use a mutable object as a dictionary key causes a `TypeError`.
  - mutable 객체를 딕셔너리 key로 사용하려고 하면, `TypeError`가 발생한다.

```python
bad_dict = {
  [1, 2, 3]: "one two three"
}

# TypeError: unhashable type: 'list'
```

[코드 실행 확인](https://code.sololearn.com/361/#py)

<br>

<br>

#### QUIZ

- Fill in the blanks to define a valid dictionary with two elements.
  - 두 엘리먼트로 유효한 딕셔너리를 정의해라.

```python
cars = {"BMW": "blue", "Volvo": "red"}
```

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
test = {}
print(test[0])
```

> `KeyError`

<br>

- Which of these values can't be used as a dictionary key?
  - 딕셔너리 key로 사용될 수 없는 값은 무엇인가?

> [ ] False
>
> [ ] "one two three"
>
> [x] `{2: 4, 3: 9, 4: 16}`

<br>

<br>