---
layout: post
title: "(Basics 09) 타입 변환"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- In Python, it's impossible to complete certain operations due to the types involved.
  - Python에서는 관련된 타입으로 인해 특정 연산을 완료할 수 없다.
- For instance, you can't add two strings containing the numbers 2 and 3 together to produce the integer 5, as the operation will be performed on strings, making the result '23'.
  - 예를 들어, 숫자 2와 3을 포함하는 두 개의 문자열을 더해서 정수 5를 출력할 수 없다.
  - 연산은 문자열에서 수행되므로, 결과는 '23'이 된다.
- The solution to this is `type conversion`.
  - 이에 대한 해결책은 `타입 변환`이다.
- In that example, you would use the `int` function.
  - 아래 예제에서는, `int` 함수를 사용한다.

```python
>>> "2" + "3"
# '23'

>>> int("2") + int("3")
# 5
```

[코드 실행 확인](https://code.sololearn.com/947/#py)

<br>

> In Python, the types we have used so far have been `integers`, `floats`, and `strings`.
>
> Python에서 지금까지 사용한 타입은 `정수`, `부동 소수점 수`, `문자열`이다.
>
> The functions used to convert to these are `int`, `float` and `str`, respectively.
>
> 이들로 변환하는 데 사용되는 함수는 각각 `int`, `float`, `str`이다.

<br>

- Another example of type conversion is turning user input (which is a `string`) to numbers (`integers` or `floats`), to allow for the performance of calculations.
  - 타입 변환의 다른 예는, 사용자 입력을 숫자로 변환해서 계산 수행을 허용하는 것이다.

```python
>>> float(input("Enter a number: ")) + float(input("Enter another number: "))
# Enter a number: 40
# Enter another number: 2
# 42.0
```

[코드 실행 확인](https://code.sololearn.com/948/#py)

<br>

> Passing non-integer or float values will cause an error.
>
> 정수가 아닌 값 또는 부동 소수점 수 값을 전달하면 에러가 발생한다.

<br>

<br>

#### QUIZ

- What is the output of this code?
  - 아래 코드의 출력은 무엇인가?

```python
>>> int("3" + "4")
```

> `34` (number)

<br>

- What is the output of this code?
  - 아래 코드의 출력은 무엇인가?

```python
float("210" * int(input("Enter a number: ")))
# Enter a number: 2
```

> `210210.0`

<br>

<br>