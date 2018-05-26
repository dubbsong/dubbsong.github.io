---
layout: post
title: "SoloLearn 번역 - 01. Functional Programming (Functional Programming)"
categories: dev
tags: python
---

## Functional Programming

- **Functional programming** is a style of programming that (as the name suggests) is based around functions.
  - **함수형 프로그래밍**은 (이름에서 알 수 있듯이) 함수를 기반으로 하는 프로그래밍 스타일이다.
- A key part of functional programming is **high-order functions**.
  - 함수형 프로그래밍의 핵심 부분은 **고차 함수**이다.
- We have seen this idea briefly in the previous lesson on functions as objects.
  - 객체로서의 함수에 대한 아이디어를 이전 강의에서 간략하게 보았었다.
- Higher-order functions take other functions as arguments, or return them as results.
  - 고차 함수는 다른 함수를 인수로 취하거나, 결과로 반환한다.

<br>

- Example:

```python
def apply_twice(func, arg):
   return func(func(arg))

def add_five(x):
   return x + 5

print(apply_twice(add_five, 10))
```

<br>

- Result:

```python
>>>
20
>>>
```

<br>

> The function **apply_twice** takes another function as its argument, and calls it twice inside its body.
>
> **apply_twice** 함수는 또 다른 함수를 인수로 취해서, 본문 내부에서 두 번 호출한다.

------

<br>

## Pure Functions (순수 함수)

- Functional programming seeks to use **pure functions**.
  - 함수형 프로그래밍은 **순수 함수**를 사용하려고 노력한다.
- Pure functions have no side effects, and return a value that depends **only** on their arguments.
  - 순수 함수는 부작용이 없으며, 인수에만 의존하는 값을 반환한다.
- This is how functions in math work: for example, The cos(x) will, for the same value of x, always return the same result.
  - 이것이 수학적으로 함수가 작동하는 방식이다. 예를 들어, cos(x)는 동일한 x 값에 대해 항상 동일한 결과를 반환한다.
- Below are examples of pure and impure functions.
  - 다음은 순수 함수와 순수하지 않은 함수의 예제이다.

<br>

- Pure function:

```python
def pure_function(x, y):
   temp = x + 2*y
   return temp / (2*x + y)
```

<br>

- Impure function:

```python
some_list = []
def impure(arg):
   some_list.append(arg)
```

<br>

> The function above is not pure, because it changed the state of **some_list**.
>
> 위의 함수는 **some_list**의 상태를 변경했으므로, 순수하지 않다.

------

<br>

## Pure Functions 02

- Using pure functions has both advantages and disadvantages.
  - 순수 함수를 사용하면 장단점이 있다.
- Pure functions are easier to reason about and test.
  - 순수 함수는 쉽게 추론하고 테스트 할 수 있다.
- Pure functions are more efficient.
  - 순수 함수는 더 효율적이다.
- Once the function has been evaluated for an input, the result can be stored and referred to the next time the function of that input is needed, reducing the number of times the function is called.
  - 입력에 대해 함수가 평가되면, 그 결과는 그 입력에 대한 함수가 필요한 다음 번에 저장되고 참조될 수 있다. 함수가 호출된 횟수도 줄일 수 있다.
- This is called **memoization**.
  - 이를 **memoization**이라고 한다.
  - `memoization`: 메모이제이션. 컴퓨터 프로그램이 동일한 계산을 반복해야 할 때, 이전에 계산한 값을 메모리에 저장함으로써 동일한 계산의 반복 수행을 제거하여 프로그램 실행 속도를 빠르게 하는 기술.
- Pure functions are easier to run in parallel.
  - 순수 함수는 병렬로 실행하기가 쉽다.

<br>

> The main disadvantage of using only pure functions is that they majorly complicate the otherwise simple task of I/O, since this appears to inherently require side effects.
>
> 순수 함수만을 사용하는 것의 가장 큰 단점은 I/O의 단순한 작업을 더 복잡하게 만든다.
>
> 이것은 본질적으로 부작용을 필요로 하기 때문에 나타나는 것이다.
>
> `I/O`: input/output

> They can also be more difficult to write in some situations.
>
> 어떤 상황에서는 작성하기가 더 어려울 수 있다.

------

<br>

## QUIZ

- What is the output of this code?

```python
def test(func, arg):
   return func(func(arg))

def mult(x):
   return x * x

print(test(mult, 2))


16
```

<br>

- Is this a pure function?
  - It depends
  - No
  - **Yes**

```python
def func(x):
   y = x**2
   z = x + y
   return z
```

<br>

- Which of these is not an advantage of using pure functions?
  - **They are easier to write**
  - They are easier to run in parallel
  - They are easier to analyze

<br>