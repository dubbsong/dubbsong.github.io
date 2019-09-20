---
layout: post
title: "(Functional Programming 06) 재귀(Recursion)"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- `Recursion` is a very important concept in functional programming.
  - `재귀`는 함수형 프로그래밍에서 아주 중요한 개념이다.
- The fundamental part of recursion is self\-reference \- functions calling themselves.
  - 재귀의 핵심 부분은 자기 참조(self\-reference)이다.
  - 자신을 호출한다.
- It is used to solve problems that can be broken up into easier sub-problems of the same type.
  - 동일한 타입의 더 쉬운 하위 문제로 나눌 수 있는 문제를 해결하는 데 사용된다.

<br>

- A classic example of a function that is implemented recursively is the `factorial` function, which finds the product of all positive integers below a specified number.
  - 재귀적으로 구현되는 함수의 전형적인 예는, `factorial(계승)` 함수이다.
  - 이 함수는 지정된 수 아래의 모든 양수의 곱을 찾는다.
- For example, 5\! (5 factorial) is 5 \* 4 \* 3 \* 2 \* 1 (120).
  - 예를 들어, 5\!는 5 \* 4 \* 3 \* 2 \* 1 (120)이다.
- To implement this recursively, notice that 5\! = 5 \* 4\!, 4\! = 4 \* 3\!, 3\! = 3 \* 2\!, and so on.
  - 이를 재귀적으로 구현하면 이와 같다.
  - 5\! = 5 \* 4\!, 4\! = 4 \* 3\!, 3\! = 3 \* 2\! 등등
- Generally, n\! = n \* (n \- 1)\!.
  - 일반적으로 n\! = n \* (n \- 1)\!이다.

- Furthemore, 1\! = 1.
  - 1\!은 1이다.
- This is known as the `base case`, as it can be calculated without performing any more factorials.
  - factorial을 더 수행하지 않고 계산될 수 있으므로, 이를 `base case`라고 한다.
- Below is a recursive implementation of the factorial function.
  - 아래 코드는 factorial 함수의 재귀적 구현이다.

```python
def factorial(x):
  if x == 1:
    return 1
  else:
    return x * factorial(x - 1)
  
print(factorial(5))
# 120 (5 * 4 * 3 * 2 * 1)
```

[코드 실행 확인](https://code.sololearn.com/395/#py)

<br>

> The `base case` acts as the exit condition of the recursion.
>
> `base case`는 재귀의 종료 조건으로 동작한다.

<br>

- Recursive functions can be infinite, just like infinite `while` loops.
  - 재귀 함수는 무한 `while` loop처럼 무한할 수 있다.
- These often occur when you forget to implement the base case.
  - 이는 base case 구현을 잊었을 때 종종 발생한다.
- Below is an incorrect version of the factorial function.
  - 아래 코드는 잘못된 버전의 factorial 함수이다.
- It has no base case, so it runs until the interpreter runs out of memory and crashes.
  - base case가 없으므로, 인터프리터에 메모리가 부족하고 충돌할 때까지 실행된다.

```python
def factorial(x):
  return x * factorial(x - 1)

print(factorial(5))
# RuntimeError: maximum recursion depth exceeded
```

[코드 실행 확인](https://code.sololearn.com/396/#py)

<br>

- Recursion can also be indirect.
  - 재귀도 간접적일 수 있다.
- One function can call a second, which calls the first, which calls the second, and so on.
  - 하나의 함수는 두 번째 함수를 호출할 수 있다.
  - 이 함수는 첫 번째 함수를 호출하고, 두 번째 함수도 호출하는 식이다.
- This can occur with any number of functions.
  - 이는 여러 함수로 발생할 수 있다.

```python
def is_even(x):
  if x == 0:
    return True
  else:
    return is_odd(x - 1)
  
def is_odd(x):
  return not is_even(x)

print(is_odd(17))
# True

print(is_even(23))
# False
```

[코드 실행 확인](https://code.sololearn.com/397/#py)

<br>

<br>

<br>

#### QUIZ

- What is the base case of a recursive function?
  - 재귀 함수의 base case는 무엇인가?

> A case that doesn't involve any further calls to that function
>
> 해당 함수를 더 이상 호출하지 않는 경우

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
def sum_to(x):
  return x + sum_to(x - 1)

print(sum_to(5))
```

> `RuntimeError`

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
def fib(x):
  if x == 0 or x == 1:
    return 1
  else:
    return fib(x - 1) + fib(x - 2)
  
print(fib(4))
```

> `5`

<br>

<br>