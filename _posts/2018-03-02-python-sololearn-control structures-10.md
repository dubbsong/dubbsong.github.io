---
layout: post
title: "SoloLearn - 10. Range (Control Structures)"
categories: dev
tags: python
---

## Range

- The **range** function creates a sequential list of numbers.
  - **range** 함수는 일련의 숫자 배열을 만든다.
- The code below generates a list containing all of the integers, up to 10.
  - 아래 코드는 최대 10개의 정수를 포함하는 배열을 생성한다.

```python
numbers = list(range(10))
print(numbers)
```

<br>

- Result:

```python
>>>
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
>>>
```

<br>

> The call to **list** is necessary because **range** by itself creates a **range object**, and this must be converted to a **list** if you want to use it as one.
>
> **range**는 자체적으로 **range 객체**를 생성하기 때문에 배열에 대한 호출이 필요하다.
>
> 그리고 이것을 하나로 사용하려면 **배열**로 변환해야 한다.

<br>

## Range 02

- If **range** is called with one argument, it produces an object with values from 0 to that argument.
  - **range**가 하나의 인수로 호출된다면, 0부터 해당 인수까지의 값을 가진 객체를 생성한다.
  - `argument`: a value passed to a function (or method) when calling it
- If it is called with two arguments, it produces values from the first to the second.
  - 두 개의 인수를 호출된다면, 첫 번째부터 두 번째까지의 값을 생성한다.
- For example:

```python
numbers = list(range(3, 8))
print(numbers)

print(range(20) == range(0, 20))
```

<br>

- Result:

```python
>>>
[3, 4, 5, 6, 7]

True
>>>
```

<br>

## Range 03

- **range** can have a third argument, which determines the interval of the sequence produced.
  - **range**는 생성된 시퀀스의 간격을 결정하는 세 번째 인수를 가질 수 있다.
- This third argument must be an integer.
  - 이 세 번째 인수는 정수여야만 한다.

```python
numbers = list(range(5, 20, 2))
print(numbers)
```

<br>

- Result:

```python
>>>
[5, 7, 9, 11, 13, 15, 17, 19]
>>>
```

<br>

## QUIZ

- What is the result of this code?

```python
nums = list(range(5))
print(nums[4])

4
```

<br>

- What is the result of this code?

```python
nums = list(range(5, 8))
print(len(nums))

3
```

<br>

- What is the result of this code?

```python
nums = list(range(3, 15, 3))
print(nums[2])

9
```

<br>