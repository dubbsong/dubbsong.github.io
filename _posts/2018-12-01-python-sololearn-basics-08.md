---
layout: post
title: "(Basics 08) 문자열 연산"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

#### Concatenation

###### 연결

<br>

- As with integers and floats, strings in Python can be added, using a process called `concatenation`, which can be done on any two strings.
  - `연결(concatenation)`이라는 프로세스를 사용해서, Python의 문자열을 추가할 수 있다.
- When concatenating strings, it doesn't matter whether they've been created with single or double quotes.
  - 문자열을 연결할 때, 작은따옴표 또는 큰따옴표로 생성되었는지는 중요하지 않다.

```python
>>> "Spam" + 'eggs'
# Spameggs

>>> print("1st str" + ", " + "2nd str")
# 1st str, 2nd str
```

[코드 실행 확인](https://code.sololearn.com/286/#py)

<br>

> You can't concatenate strings with numbers (integers).
>
> 문자열을 숫자(정수)로 연결할 수 없다.

<br>

- Even if your strings contain numbers, they are still added as strings rather than integers.
  - 문자열에 숫자가 포함되어 있더라도, 정수가 아닌 문자열로 추가된다.
- Adding a string to a number produces an error, as even though they might look similar, they are two different entities.
  - 문자열을 숫자에 추가하면 에러가 발생할 수 있다.
  - 비슷해 보이지만, 서로 다른 독립체이다.

```python
>>> "2" + "2"
# 22

>>> 1 + '2' + 3 + '4'
# TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

[코드 실행 확인](https://code.sololearn.com/946/#py)

<br>

<br>

#### String Operations

###### 문자열 연산

<br>

- Strings can also be `multiplied` by integers.
  - 문자열에 정수를 곱할 수도 있다.
- This produces a repeated version of the original string.
  - 문자열에 정수를 곱하면, 원래 문자열의 반복된 버전이 생성된다.
- The order of the string and the integer doesn't matter, but the string usually comes first.
  - 문자열과 정수의 순서는 중요하지 않지만, 일반적으로 문자열이 우선한다.

<br>

- Strings can't be multiplied by other strings.
  - 문자열에 다른 문자열을 곱할 수 없다.
- Strings also can't be multiplied by floats, even if the floats are whole numbers.
  - 부동 소수점 수(float)가 정수라 하더라도, 문자열에 부동 소수점 수를 곱할 수 없다.

```python
>>> print("spam" * 3)
# spamspamspam

>>> '2' * 4
# 2222

>>> '17' * '87'
# TypeError: can't multiply sequence by non-int of type 'str'

>>> 'pythonisfun' * 7.0
# TypeError: can't multiply sequence by non-int of type 'float'
```

[코드 실행 확인](https://code.sololearn.com/287/#py)

<br>

<br>

#### QUIZ

- Which line of code produces an error?
  - 어떤 코드가 에러를 발생시키는가?

> [] 3 + 4
>
> [] "7" + 'eight'
>
> [] "one" + "2"
>
> [x] `'5' + 6`

<br>

- What is the output of this code?
  - 아래 코드의 출력은 무엇인가?

```python
>>> print('7' * 3)
```

> `777`

<br>

<br>