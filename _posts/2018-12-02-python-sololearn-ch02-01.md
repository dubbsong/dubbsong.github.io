---
layout: post
title: "(Control Structures 01) 불리언(Boolean)과 비교"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

## Booleans

###### 불리언

<br>

- Another type in Python is the `Boolean` type.
  - Python의 또 다른 타입은 `불리언(Boolean)` 타입이다.
- There are two Boolean values: `True` and `False`.
  - 불리언 값은 `True`와 `False` 두 가지가 있다.
- They can be created by comparing values, for instance by using the equal operator ==.
  - 값을 비교해서 생성할 수 있다.
  - 예를 들어, 등호 연산자 ==를 사용한다.

```python
>>> my_boolean = True
>>> my_boolean
# True

>>> 2 == 3
>>> False

>>> "hello" == "hello"
# True
```

[코드 실행 확인](https://code.sololearn.com/294/#py)

<br>

> Be careful not to confuse `assignment` (one equals sign) with `comparison` (two equals signs).
>
> `할당`(등호 1개)과 `비교`(등호 2개)를 혼동하지 않도록 주의한다.

<br>

## Comparison

###### 비교

<br>

- Another comparison operator, the `not equal` operator(\!=), evaluates to `True` if the items being compared aren't equal, and `False` if they are.
  - 또 다른 비교 연산자인 `not equal` 연산자(\!=)는, 비교 중인 항목이 같지 않으면 `True`로 평가되고, 비교 중인 항목이 같으면 `False`로 평가된다.

```python
>>> 1 != 1
# False

>>> "eleven" != "seven"
# True

>>> 2 != 10
# True
```

[코드 실행 확인](https://code.sololearn.com/295/#py)

<br>

- Python also has operators that determine whether one number (float or integer) is greater than or smaller than another.
  - Python에는 하나의 숫자(부동 소수점 수 또는 정수)가 다른 숫자보다 큰지 작은지를 결정하는 연산자도 있다.
- These operators are \> and \< respectively.
  - 이러한 연산자는 각각 \>와 \<이다.

```python
>>> 7 > 5
# True

>>> 10 < 10
# False
```

[코드 실행 확인](https://code.sololearn.com/296/#py)

<br>

- The greater than or equal to, and smaller than or equal to operators are \>= and \<=.
  - 크거나 같은 연산자는 \>=이다.
  - 작거나 같은 연산자는 \<=이다.

```python
>>> 7 <= 8
# True

>>> 9 >= 9.0
# True
```

[코드 실행 확인](https://code.sololearn.com/297/#py)

<br>

> Greater than and smaller than operators can also be used to compare strings `lexicographically` (the alphabetical order of words is based on the alphabetical order of their component letters).
>
> 문자열을 사전순(알파벳순)으로 비교할 수도 있다.

<br>

<br>

#### QUIZ

- What are the two Boolean values in Python?
  - Python에서 두 불리언 값은 무엇인가?

> `True` and `False`

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
>>> 7 != 8
```

> `True`

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
>>> 7 > 7.0
```

> `False`

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
>>> 8.7 <= 8.70
```

> `True`

<br>

<br>