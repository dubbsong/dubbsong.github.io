---
layout: post
title: "(More Type 05) 리스트 슬라이스(slice)"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- `List slices` provide a more advanced way of retrieving values from a list.
  - `리스트 슬라이스`는 리스트에서 값을 검색하는 더 나은 방법을 제공한다.
- Basic list slicing involves indexing a list with `two colon-separated integers`.
  - 리스트 슬라이스에는, `두 개의 콜론으로 구분된 정수`로 리스트를 색인화하는 작업이 포함되어 있다.
- This returns a new list containing all the values in the old list between the indices.
  - 이는 이전 리스트에 있는 모든 값을 포함하는 새로운 리스트를 반환한다.

```python
squares = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

print(squares[2:6])
# [4, 9, 16, 25]

print(squares[3:8])
# [9, 16, 25, 36, 49]

print(squares[0:1])
# 0
```

[코드 실행 확인](https://code.sololearn.com/368/#py)

<br>

> Like the arguments to `range`, the first index provided in a slice is included in the result, but the second isn't.
>
> `range`의 인수와 마찬가지로, 슬라이스에 제공된 첫 번째 인덱스는 결과에 포함되지만, 두 번째 인덱스는 결과에 포함되지 않는다.

<br>

- If the first number in a slice is omitted, it is taken to be the start of the list.
  - 슬라이스의 첫 번째 숫자를 생략하면, 리스트의 시작으로 간주된다.
- If the second number is omitted, it is taken to be the end.
  - 두 번째 숫자를 생략하면, 리스트의 끝으로 간주한다.

```python
squares = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

print(squares[:4])
# [0, 1, 4, 9]

print(squares[7:])
# [49, 64, 81]
```

[코드 실행 확인](https://code.sololearn.com/369/#py)

<br>

> Slicing can also be done on tuples.
>
> 튜플에서 슬라이스를 수행할 수도 있다.

<br>

- List slices can also have a third number, representing the step, to include only alternate values in the slice.
  - 리스트 슬라이스에는 단계를 나타내는 세 번째 숫자가 있다.
  - 슬라이스의 대체 값만 포함된다.

```python
squares = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

print(squares[::2])
# [0, 4, 16, 36, 64]

print(squares[2:8:3])
# [4, 25]
```

[코드 실행 확인](https://code.sololearn.com/370/#py)

<br>

> \[2:8:3\] will include elements starting from the 2nd index up to the 8th with a step of 3.
>
> [2:8:3\]에는 두 번째부터 여덟 번째까지의 엘리먼트가 세 단계로 포함된다.

<br>

- `Negative` values can be used in list slicing (and normal list indexing).
  - `음수` 값이 리스트 슬라이스에서 사용될 수 있다.
- When negative values are used for the first and second values in a slice (or a normal index), they count from the end of the list.
  - 슬라이스의 첫 번째 및 두 번째 값에 음수를 사용하면, 리스트의 끝에서부터 계산된다.

```python
squares = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

print(squares[1:-1])
# [1, 4, 9, 16, 25, 36, 49, 64]
```

[코드 실행 확인](https://code.sololearn.com/371/#py)

<br>

> If a negative value is used for the step, the slice is done backwards.
>
> 단계에 음수 값이 사용되는 경우, 슬라이스는 거꾸로 수행된다.
>
> Using `[::-1]` as a slice is a common and idiomatic way to reverse a list.
>
> `[::-1]`를 슬라이스로 사용하는 것은, 리스트를 반전하는 일반적이고 관용적인 방법이다.

<br>

<br>

#### QUIZ

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
sqs = [0, 1, 4, 9, 16, 25, 36, 49, 64]

print(sqs[4:7])
```

> `[16, 25, 36]`

<br>

- Fill in the blanks to take the first two elements of the list:
  - 리스트의 처음 두 엘리먼트를 출력해라.

```python
list = ["a", "b", "c", "d"]
print(list[0:2])
```

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
sqs = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

print(sqs[1::4])
```

> `[1, 25, 81]`

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
sqs = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

print(sqs[7:5:-1])
```

> `[49, 36]`

<br>

<br>