---
layout: post
title: "(Basics 04) float (부동 소수점 수)"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- `Floats` are used in Python to represent numbers that aren't integers.
  - `float(부동 소수점 수)`은 정수가 아닌 숫자를 나타내기 위해 사용된다.

> `부동 소수점 수 (a floating point number)`
>
> 정수나 소수에 10의 정수 제곱을 곱한 수.
>
> 하나의 실수를 가수부와 지수부로 나누어 표현한다. (`±(1.가수부)x2^지수부-127`)
>
> 컴퓨터에서 실수는, 정수와 마찬가지로 2진수로만 표현해야 한다.
>
> 대부분의 시스템에서 부동 소수점 방식으로 실수를 표현한다.
>
> 컴푸터에서 실수를 가지고 수행하는 모든 연산에는 언제나 작은 오차가 존재하게 된다.

<br>

- They can be created directly by entering a number with a decimal point, or by using operations such as division on integers.
  - 소수점으로 숫자를 입력하거나, 정수 나누기와 같은 연산을 사용해서 직접 생성할 수 있다.
- Extra zeros at the number's end and are ignored.
  - 숫자 끝 여분의 0은 무시된다.

```python
>>> 3 / 4
# 0.75

>>> 9.8765000
# 9.8765
```

<br>

> Computers can't store floats perfectly accurately, in the same way that we can't write down the complete decimal expansion of 1/3 (0.3333...).
>
> 1/3의 완전한 소수 전개를 작성할 수 없는 것과 같이, 컴퓨터도 float을 완전히 정확하게 저장할 수 없다.
>
> Keep this in mind, because it often leads to infuriating bugs.
>
> 이 점을 염두에 두자.
>
> 종종 짜증나는 버그로 이어진다.

<br>

- As you saw previously, dividing any two integers produces a `float`.
  - 앞에서 보았듯이, 두 정수를 나누면 `float`이 생성된다.
- A float is also produced by running an operation on two floats, or on a float and an integer.
  - float은 두 개의 float 또는 float과 정수의 연산을 실행해서 생성된다.

```python
>>> 8 / 2
# 4.0

>>> 6 * 7.0
# 42.0

>>> 4 + 1.65
# 5.65
```

<br>

> A float can be added to an integer, because Python silently converts the integer to a float.
>
> Python은 정수를 float으로 자동 변환하므로, float을 정수에 추가할 수 있다.
>
> However, this implicit conversion is the exception rather the rule in Python \- usually you have to convert values manually if you want to operate on them.
>
> 하지만 이 암시적 변환은 Python의 규칙이 아닌 예외(exception)이다.
>
> 보통 값을 수동으로 변환해야 한다.

<br>

<br>

#### QUIZ

- Which of these will not be stored as a float?
  - float으로 저장될 수 없는 것은 무엇인가?

> [] 2/4
>
> [] 7.0
>
> [x] `7`

<br>

- Fill in the blank with the output of this code.
  - 다음 코드의 출력은 무엇인가?

```python
>>> 1 + 2 + 3 + 4.0 + 5
```

> `15.0`

<br>

<br>