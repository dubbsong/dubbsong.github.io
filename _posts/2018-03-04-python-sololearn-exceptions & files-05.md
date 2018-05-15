---
layout: post
title: "SoloLearn 번역 - 05. Assertions (Exceptions & Files)"
categories: dev
tags: python
---

## Assertions (assert 문)

- An **assertion** is a sanity-check that you can turn on or turn off when you have finished testing the program.
  - **assertion**은 프로그램 테스트를 마쳤을 때 켜거나 끌 수 있는 위생 검사이다.
- An expression is tested, and if the result comes up false, an exception is raised.
  - 표현식이 테스트되고, 결과가 false가 되면, 예외가 발생한다.
- Assertions are carried out through use of the **assert** statement.
  - Assertion은 **assert** 문을 사용해서 수행된다.

```python
print(1)
assert 2 + 2 == 4
print(2)
assert 1 + 1 == 3
print(3)
```

<br>

- Result:

```python
>>>
1
2
AssertionError
>>>
```

<br>

> Programmers often place assertions at the start of a function to check for valid input, and after a function call to check for valid output.
>
> 프로그래머는 종종 assertion을 함수의 시작에 배치한다. 유효한 입력을 검사하고, 호출 후에 유효한 출력을 검사하기 위해.

------

<br>

## Assertions 02

- The **assert** can take a second argument that is passed to the AssertionError raised if the assertion fails.
  - assert 문은 assertion이 실패한 경우 발생하는 AssertionError에 전달된 두 번째 인수를 가져올 수 있다.

```python
temp = -10
assert(temp >= 0), "Colder than absolute zero!"
```

<br>

- Result:

```python
>>>
AssertionError: Colder than absolute zero!
>>>
```

<br>

> AssertionError exceptions can be caught and handled like any other exception using the **try-except** statement, but if not handled, this type of exception will terminate the program.
>
> AssertionError 예외는 **try-except** 문을 사용하는 다른 예외와 마찬가지로 catch되고 처리될 수 있지만, 만약 처리되지 않는다면, 이 예외 타입은 프로그램을 종료할 것이다.

------

<br>

## QUIZ

- What is the highest number printed by this code?

```python
print(0)
assert "h" != "w"
print(1)
assert False
print(2)
assert True
print(3)


1
```

<br>

- Fill in the blanks to define a function that takes one argument. Assert the argument to be positive.

```python
def my_func(x):
   assert x > 0, "Error!"
   print(x)
```

<br>