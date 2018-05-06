---
layout: post
title: "SoloLearn - 09. Type Conversion"
categories: dev
tags: python
---

## Type Conversion 01 (형 변환)

- In Python, it's impossible to complete certain operations due to the types involved.
  - Python에서는, 관련 유형 때문에 확실한 연산을 완료하는 것이 불가능하다.
- For instance, you can't add two strings containing the numbers 2 and 3 together to produce the integer 5, as the operation will be performed on strings, making the result '23'.
  - 예를 들어, 숫자 2와 3을 포함하는 두 개의 문자열을 더해서 정수 5를 생성할 수 없다. 문자열에서 연산이 수행되기 때문에, 결과가 '23'이 된다.
- The solution to this is **type conversion**.
  - 해결책은 **형 변환**이다.
- In that example, you would use the **int** function.
  - 이 예제에서는, **int** 함수를 사용해야 한다.

```python
>>> "2" + "3"
'23'

>>> int("2") + int("3")
5
```

<br>

> In Python, the types we have used so far have been **integers**, **floats**, and **strings**.
>
> Python에서, 지금까지 사용했던 타입은 **정수**, **부동 소수점**, **문자열**이다.

> The functions used to convert to these are **int**, **float** and **str**, respectively.
>
> 변환하는 데에 사용되는 함수는 각각 **int**, **float**, **str**이다.

<br>

## Type Conversion 02

- Another example of type conversion is turning user input (which is a string) to numbers (integers or floats), to allow for the performance of calculations.
  - 형 변환의 또 다른 예제는 유저 입력(문자열)을 숫자(정수 또는 부동 소수점)로 변환해서, 계산 수행을 허용하는 것이다.

```python
>>> float(input("Enter a number: ")) + float(input("Enter another number: "))
Enter a number: 40
Enter another number: 2

42.0
```

<br>

## QUIZ

- What is the output of this code?

```python
>>> int("3" + "4")
34
```

<br>

- What is the output of this code?

```python
>>> float("210" * int(input("Enter a number: ")))
Enter a number: 2

210210.0
```

<br>