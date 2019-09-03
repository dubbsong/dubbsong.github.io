---
layout: post
title: "(Control Structures 04) 불리언 로직"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- `Boolean logic` is used to make more complicated conditions for `if` statements that rely on more than one condition.
  - `불리언 로직`은 둘 이상의 조건에 의존하는 `if` 문에 대해 보다 복잡한 조건을 생성하는 데 사용된다.
- Python's Boolean operators are `and`, `or`, and `not`.
  - Python의 불리언 연산자는 `and`, `or`, `not`이다.
- The `and` operator takes two arguments, and evaluates as `True` if, and only if, both of its arguments are `True`.
  - `and` 연산자는 두 개의 인수를 사용한다.
  - 두 인수 모두 `True`인 경우에만 `True`로 평가한다.
- Otherwise, it evaluates to `False`.
  - 그렇지 않으면 `False`로 평가한다.

```python
>>> 1 == 1 and 2 == 2
# True

>>> 1 == 1 and 2 == 3
# False

>>> 1 != 1 and 2 == 2
# False

>>> 2 < 1 and 3 > 6
# False
```

[코드 실행 확인](https://code.sololearn.com/303/#py)

<br>

> Python uses words for its Boolean operators, whereas most other languages use symbols such as \&\&, \|\| and \!.
>
> Python은 불리언 연산자에 단어를 사용한다.
>
> 대부분의 다른 언어는 \&\&, \|\|, \!를 사용한다.

<br>

- The `or` operator also takes two arguments.
  - `or` 연산자도 두 가지 인수를 사용한다.
- It evaluates to `True` if either (or both) of its arguments are `True`, and `False` if both arguments are `False`.
  - 인수 중 하나(또는 둘 모두)가 `True`로 평가되면 `True`이다.
  - 두 인수 모두 `False`로 평가되면 `False`이다.

```python
>>> 1 == 1 or 2 == 2
# True

>>> 1 == 1 or 2 == 3
# True

>>> 1 != 1 or 2 == 2
# True

>>> 2 < 1 or 3 > 6
# False
```

[코드 실행 확인](https://code.sololearn.com/304/#py)

<br>

- Unlike other operators we've seen so far, `not` only takes one argument, and inverts it.
  - 지금까지 본 연산자들과는 달리, `not`은 하나의 인수를 사용하고, 뒤집는다.
- The result of `not True` is `False`, and `not False` goes to `True`.
  - `not True`는 결과가  `False`이고, `not False`는 결과가 `True`이다.

```python
>>> not 1 == 1
# False

>>> not 1 > 7
# True
```

[코드 실행 확인](https://code.sololearn.com/305/#py)

<br>

> You can chain multiple conditional statements in an `if` statement using the Boolean operators.
>
> 불리언 연산자를 사용해서 `if` 문에 여러 조건문을 연결할 수 있다.

<br>

<br>

#### QUIZ

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
if (1 == 1) and (2 + 2 > 3):
  print("true")
else:
  print("false")
```

> `true`

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
if not True:
  print("1")
elif not (1 + 1 == 3):
  print("2")
else:
  print("3")
```

> `2`

<br>

<br>