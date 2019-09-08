---
layout: post
title: "(Exceptions & Files 05) assert 문"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- An `assertion` is a sanity-check that you can turn on or turn off when you have finished testing the program.
  - `assertion`은 프로그램 테스트를 끝냈을 때 켜거나 끌 수 있는 상태 체크(sanity-check)이다.
- An expression is tested, and if the result comes up false, an exception is raised.
  - 표현식이 테스트되고 결과가 거짓인 경우, 예외가 발생한다.
- Assertions are carried out through use of the `assert` statement.
  - `assertion`은 `assert` 문을 사용해서 수행된다.

```python
print(1)
assert 2 + 2 == 4
print(2)
assert 1 + 1 == 3
print(3)

# 1
# 2
# AssertionError
```

[코드 실행 확인](https://code.sololearn.com/352/#py)

<br>

> Programmers often place assertions at the start of a function to check for valid input, and after a function call to check for valid output.
>
> 프로그래머는 종종 함수 시작 시 유효한 입력 확인을 위해, 함수 호출 후 유효한 출력을 확인하기 위해 assert 문을 위치시킨다.

<br>

- The `assert` can take a second argument that is passed to the AssertionError raised if the assertion fails.
  - `assert`는 두 번째 인수를 사용할 수 있다.

```python
temp = -10
assert(temp >= 0), "Colder than absolute zero!"

# AssertionError: Colder than absolute zero!
```

[코드 실행 확인](https://code.sololearn.com/353/#py)

<br>

<br>

#### QUIZ

- What is the highest number printed by this code?
  - 이 코드로 출력된 가장 큰 숫자는 무엇인가?

```python
print(0)
assert "h" != "w"
print(1)
assert False
print(2)
assert True
print(3)
```

> `1`

<br>

<br>