---
layout: post
title: "SoloLearn 번역 - 05. List Slices (More Types)"
categories: dev
tags: python
---

## List Slices (배열 slice)

- **List slices** provide a more advanced way of retrieving values from a list.
  - **배열 slices**는 배열에서 값을 검색하는 것보다 더 나은 방법을 제공한다.
- Basic list slicing involves indexing a list with **two colon-separated integers**.
  - 기본 배열 슬라이싱에는 **콜론으로 구분된 두 개의 정수**로 배열을 인덱싱하는 것이 포함된다.
- This returns a new list containing all the values in the old list between the indices.
  - 이것은 이전 배열의 인덱스 사이에 있는 모든 값을 포함하는 새로운 배열을 반환한다.

<br>

- Example:

```python
squares = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
print(squares[2:6])
print(squares[3:8])
print(squares[0:1])
```

<br>

- Result:

```python
>>>
[4, 9, 16, 25]
[9, 16, 25, 36, 49]
[0]
>>>
```

<br>

> Like the arguments to **range**, the first index provided in a slice is included in the result, but the second isn't.
>
> **range**에 대한 인수와 마찬가지로, 슬라이스에 제공된 첫 번째 인덱스는 결과에 포함되지만, 두 번째 인덱스는 결과에 포함되지 않는다.

------

<br>

## List Slices 02

- If the first number in a slice is omitted, it is taken to be the start of the list.
  - 슬라이스의 첫 번째 숫자가 생략된다면, 배열의 시작으로 간주된다.
- If the second number is omitted, it is taken to be the end.
  - 두 번째 숫자가 생략된다면, 끝으로 간주된다.

<br>

- Example:

```python
squares = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
print(squares[:7])
print(squares[7:])
```

<br>

- Result:

```python
>>>
[0, 1, 4, 9, 16, 25, 36]
[49, 64, 81]
>>>
```

<br>

> Slicing can also be done on tuples.
>
> 슬라이싱은 tuple에서도 수행할 수 있다.

------

<br>

## List Slices 03

- List slices can also have a third number, representing the step, to include only alternate values in the slice.
  - 배열 슬라이스는 단계를 나타내는 세 번째 숫자가 있어서, 슬라이스에 다른 값만 포함할 수 있다.

```python
squares = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
print(squares[::2])
print(squares[2:8:3])
```

<br>

- Result:

```python
>>>
[0, 4, 16, 36, 64]
[4, 25]
>>>
```

<br>

> [2:8:3] will include elements starting from the 2nd index up to the 8th with a step of 3.
>
> [2:8:3]은 두 번째 인덱스부터 시작해서 8단계 중 3단계까지의 요소가 포함된다.

------

<br>

## List Slices 04

- **Negative** values can be used in list slicing (and normal list indexing).
  - **음수** 값은 배열 슬라이싱(및 일반 배열 인덱싱)에 사용될 수 있다.
- When negative values are used for the first and second values in a slice (or a normal index), they count from the end of the list.
  - 음수 값이 슬라이스의 첫 번째와 두 번째 값(또는 일반 인덱스)에 사용되면, 배열의 끝에서부터 카운트된다.

```python
squares = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
print(squares[1:-1])
```

<br>

- Result:

```python
>>>
[1, 4, 9, 16, 25, 36, 49, 64]
>>>
```

<br>

> If a negative value is used for the step, the slice is done backwards.
>
> 만약 음수 값이 단계에 사용된다면, 슬라이스가 거꾸로 수행된다.

> Using [::-1] as a slice is a common and idiomatic way to reverse a list.
>
> 슬라이스로 [::-1]을 사용하는 것은 배열을 뒤집는 공통적이고 관용적인 방법이다.

------

<br>

## QUIZ

- What is the result of this code?
  - [16, 25, 36, 49]
  - [25, 36, 49]
  - **[16, 25, 36]**

```python
sqs = [0, 1, 4, 9, 16, 25, 36, 49, 64]
print(sqs[4:7])
```

<br>

- Fill in the blanks to take the first two elements of the list:

```python
list = ["a", "b", "C", "d"]
a = list[0:2]
```

<br>

- What is the output of this code?
  - An error occurs
  - [0, 1, 4]
  - **[1, 25, 81]**
  - [1, 25]

```python
sqs = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
print(sqs[1::4])
```

<br>

- What is the output of this code?
  - [49]
  - []
  - **[49, 36]**

```python
sqs = [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
print(sqs[7:5:-1])
```

<br>