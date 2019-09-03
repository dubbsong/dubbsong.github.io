---
layout: post
title: "(Basics 11) In-Place 연산자"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- `In-place operators` allow you to write code like 'x = x \+ 3' more concisely, as 'x \+= 3'.
  - `In-place 연산자`를 사용하면 'x = x \+ 3' 코드를 'x \+= 3' 코드로 더 간결하게 작성할 수 있다.
- The same thing is possible with other operators such as \-, \*, / and % as well.
  - \-, \*, /, %와 같은 다른 연산자도 마찬가지이다.

```python
>>> x = 2
>>> print(x)
# 2

>>> x += 3
>>> print(x)
# 5
```

[코드 실행 확인](https://code.sololearn.com/291/#py)

<br>

- These operators can be used on types other than numbers, as well, such as `strings`.
  - 이러한 연산자는 `문자열`과 같은 숫자 이외의 타입에도 사용할 수 있다.

```python

```

[코드 실행 확인](https://code.sololearn.com/292/#py)

<br>

> Many other languages have special operators such as '\+\+' as a shortcut for 'x \+= 1'.
>
> 다른 많은 언어에는 'x \+= 1'의 단축으로 '\+\+'와 같은 특수 연산자가 있다.
>
> Python `does not` have these.
>
> Python에는 이러한 특수 연산자가 `없다`.

<br>

<br>

#### QUIZ

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
>>> x = 4
>>> x *= 3
>>> print(x)
```

> `12`

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
>>> x = "a"
>>> x *= 3
>>> print(x)
```

> `aaa`

<br>

<br>