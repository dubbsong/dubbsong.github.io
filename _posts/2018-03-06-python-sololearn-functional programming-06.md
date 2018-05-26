---
layout: post
title: "SoloLearn 번역 - 06. Recursion (Functional Programming)"
categories: dev
tags: python
---

## Recursion (재귀)

- **Recursion** is a very important concept in functional programming.
  - **재귀**는 함수형 프로그래밍에서 매우 중요한 개념이다.
- The fundamental part of recursion is self-reference - functions calling themselves.
  - 재귀의 근본적인 부분은 자기 참조 - 스스로를 호출하는 함수이다.
- It is used to solve problems that can be broken up into easier sub-problems of the same type.
  - 동일한 타입의 하위 문제로 분해될 수 있는 문제를 해결하는 데 사용된다.

<br>

- A classic example of a function that is implemented recursively is the **factorial** function, which finds the product of all positive integers below a specified number.
  - 재귀적으로 구현되는 함수의 전형적인 예는 **팩토리얼** 함수이다.
  - 이 팩토리얼 함수는 지정된 숫자 이하의 모든 양의 정수의 결과를 찾는다.
- For example, 5! (5 factorial) is 5 * 4 * 3 * 2 * 1 (120).
  - 예를 들어, 5! (5 팩토리얼)은 5 * 4 * 3 * 2 * 1 (120)이다.
- To implement this recursively, notice that 5! = 5 * 4!, 4! = 4 * 3!, 3! = 3 * 2!, and so on.
  - 이것을 재귀적으로 구현하려면, 5! = 5 * 4!, 4! = 4 * 3!, 3! = 3 * 2! 등이 있다.
- Generally, n! = n * (n - 1)!.
  - 일반적으로 n! = n * (n - 1)!이다.
- Furthermore, 1! = 1.
  - 게다가 !1 = 1이다.
- This is known as the **base case**, as it can be calculated without performing any more factorials.
  - 이것은 더 이상 계승을 수행하지 않고 계산할 수 있기 때문에 **base case**라고 한다.
- Below is a recursive implementation of the factorial function.
  - 아래는 팩토리얼 함수의 재귀 구현이다.

```python
def factorial(x):
   if x == 1:
      return 1
   else:
      return x * factorial(x - 1)
   
print(factorial(5))
```

<br>

- Result:

```python
>>>
120
>>>
```

<br>

> The **base case** acts as the exit condition of the recursion.
>
> **base case**는 재귀의 종료 조건으로 사용된다.

------

<br>

## Recursion 02

- Recursive functions can be infinite, just like infinite **while** loops.
  - 재귀 함수는 무한 **while** 루프처럼 무한할 수 있다.
- These often occur when you forget to implement the base case.
  - 이것들은 base case를 구현하는 것을 잊었을 때 종종 발생한다.
- Below is an incorrect version of the factorial function.
  - 다음은 팩토리얼 함수의 잘못된 버전이다.
- It has no base case, so it runs until the interpreter runs out of memory and crashes.
  - base case는 없으므로, 인터프리터의 메모리가 부족해서 충돌할 때까지 실행된다.

```python
def factorial(x):
   return x * factorial(x - 1)

print(factorial(5))
```

<br>

- Result:

```python
>>>
RuntimeError: maximum recursion depth exceeded
>>>
```

<br>

------

<br>

## Recursion 03

- Recursion can also be indirect.
  - 재귀는 간접적일 수도 있다.
- One function can call a second, which calls the first, which calls the second, and so on.
  - 하나의 함수는 두 번째 함수를 호출할 수 있다. 두 번째 함수는 첫 번째 함수를 호출하고, 두 번째 함수는 두 번째 함수를 호출한다.
- This can occur with any number of functions.
  - 이는 여러 가지 함수로 발생할 수 있다.

<br>

- Example:

```python
def is_even(x):
   if x == 0:
      return True
   else:
      return is_odd(x - 1)
   
def is_odd(x):
   return not is_even(x)

print(is_odd(17))
print(is_even(23))
```

<br>

- Result:

```python
>>>
True
False
>>>
```

------

<br>

## QUIZ

- What is the base case of a recursive function?
  - A case involving the number 1
  - A case that never occurs
  - **A case that doesn't involve any further calls to that function**

<br>

- What is the result of this code?
  - 15
  - **RuntimeError**
  - 5

```python
def sum_to(x):
   return x + sum_to(x - 1)
print(sum_to(5))
```

<br>

- What is the result of this code?

```python
def fib(x):
   if x == 0 or x == 1:
      return 1
   else:
      return fib(x - 1) + fib(x - 2)
print(fib(4))


5
```

<br>