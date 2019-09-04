---
layout: post
title: "(Control Structures 10) range 함수"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- The `range` function creates a sequential list of numbers.
  - `range` 함수는 일련의 숫자 리스트를 생성한다.
- The code below generates a list containing all of the integers, up to 10.
  - 아래 코드는 10까지의 모든 정수를 포함하는 리스트를 생성한다.

```python
numbers = list(range(10))
print(numbers)

# [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

[코드 실행 확인](https://code.sololearn.com/323/#py)

<br>

> The call to `list` is necessary because `range` by itself creates a `range object`, and this must be converted to a `list` if you want to use it as one.
>
> `range`는 그 자체로 `range 객체`를 생성하기 때문에,  `리스트`에 대한 호출이 필요하다.
>
> 이를 사용하려면 `리스트`로 변환해야 한다.

<br>

- If `range` is called with one argument, it produces an object with values from 0 to that argument.
  - `range`가 하나의 인수로 호출되면, 0에서 해당 인수까지의 값을 가진 객체가 생성된다.
- If it is called with two arguments, it produces values from the first to the second.
  - 두 개의 인수로 호출되면, 첫 번째에서 두 번째까지의 값을 생성한다.

```python
print(range(20) === range(0, 20))
# True

numbers = list(range(3, 8))
print(numbers)
# [3, 4, 5, 6, 7]
```

[코드 실행 확인](https://code.sololearn.com/324/#py)

<br>

- `range` can have a third argument, which determines the interval of the sequence produced.
  - `range`는 세 번째 인수를 가질 수 있다.
  - 세 번째 인수는 생성된 sequence의 간격을 결정한다.
- This third argument must be an integer.
  - 세 번째 인수는 정수여야 한다.

```python
numbers = list(range(5, 20, 2))
print(numbers)

# [5, 7, 9, 11, 13, 15, 17, 19]
```

[코드 실행 확인](https://code.sololearn.com/325/#py)

<br>

<br>

#### QUIZ

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
nums = list(range(5))
print(nums[4])
```

> `4`

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
nums = list(range(5, 8))
print(len(nums))
```

> `3`

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
nums = list(range(3, 15, 3))
print(nums[2])
```

> `9`

<br>

<br>