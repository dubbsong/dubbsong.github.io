---
layout: post
title: "(Functional Programming 01) 함수형 프로그래밍"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- `Functional programming` is a style of programming that (as the name suggests) is based around functions.
  - `함수형 프로그래밍`은 이름에서 알 수 있듯이, 함수를 기반으로 하는 프로그래밍 스타일이다.
- A key part of functional programming is `higher-order functions`.
  - 함수형 프로그램의 핵심 부분은, `고차 함수`이다.
- We have seen this idea briefly in the previous lesson on functions as objects.
  - 객체로서의 함수에 대해, 이전 레슨에서 간단히 보았다.
- Higher-order functions take other functions as arguments, or return them as results.
  - 고차 함수는 다른 함수를 인수로 사용하거나, 결과로 반환한다.

```python
def apply_twice(func, arg):
  return func(func(arg))

def add_five(x):
  return x + 5

print(apply_twice(add_five, 10))
# 20
```

[코드 실행 확인](https://code.sololearn.com/381/#py)

<br>

> The function `apply_twice` takes another function as its argument, and calls it twice inside its body.
>
> `apply_twice` 함수는 다른 함수를 인수로 사용한다.
>
> 그리고 body 내에서 두 번 호출한다.

<br>

## Pure Functions

###### 순수 함수

- Functional programming seeks to use `pure functions`.
  - 함수형 프로그래밍은 `순수 함수` 사용을 추구한다.
- Pure functions have no side effects, and return a value that depends `only` on their arguments.
  - 순수 함수에는 부작용(side effect)이 없다.
  - 그리고 인수에만 의존하는 값을 반환한다.
- This is how functions in math work: for example, The cos(x) will, for the same value of x, always return the same result.
  - 예를 들어, cos(x)는 x의 동일한 값에 대해 항상 동일한 결과를 반환한다.
- Below are examples of pure and impure functions.
  - 아래 코드는 순수와 순수하지 않은 함수의 예이다.

<br>

###### Pure function:

```python
def pure_function(x, y):
  temp = x + 2 * y
  return temp / (2 * x + y)
```

###### Impure function:

```python
some_list = []

def impure(arg):
  some_list.append(arg)
```

<br>

> The function above is not pure, because it changed the state of `some_list`.
>
> 위의 함수는 `some_list`의 상태를 변경했으므로, 순수하지 않다.

<br>

- Using pure functions has both advantages and disadvantages.
  - 순수 함수 사용에는 장단점이 있다.

- Pure functions are:
  - 순수 함수는 다음과 같다.

<br>

1. easier to reason about and test.
   - 쉽게 추론하고 테스트 할 수 있다.
2. more efficient. Once the function has been evaluated for an input, the result can be stored and referred to the next time the function of that input is needed, reducing the number of times the function is called. This is called `memoization`.
   - 더 효율적이다.
   - 함수가 입력에 대해 평가되면, 다음에 해당 입력이 필요할 때 결과를 저장하고 참조해서 함수 호출을 횟수를 줄인다.
   - 이를 `memoization`이라고 한다.
3. easier to run in parallel.
   - 병렬로 더 쉽게 실행할 수 있다.

<br>

> **memoization (메모이제이션):**
>
> 컴퓨터 프로그램이 동일한 계산을 반복해야 할 때, 이전에 계산한 값을 메모리에 저장함으로써 동일한 계산의 반복 수행을 제거하여 프로그램 실행 속도를 빠르게 하는 기술.

<br>

> The main disadvantage of using only pure functions is that they majorly complicate the otherwise simple task of I/O, since this appears to inherently require side effects.
>
> 순수 함수만 사용하는 것의 주요 단점은, I/O(입출력)의 단순한 작업을 아주 복잡하게 한다는 것이다.
>
> They can also be more difficult to write in some situations.
>
> 어떤 상황에서는 작성하기가 더 어려울 수도 있다.

<br>

<br>

#### QUIZ

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
def test(func, arg):
  return func(func(arg))

def mult(x):
  return x * x

print(test(mult, 2))
```

> `16`

<br>

- Is this a pure function?
  - 아래 코드는 순수 함수인가?

```python
def func(x):
  y = x ** 2
  z = x + y
  return z
```

> `Yes`

<br>

- Which of these is not an advantage of using pure functions?
  - 다음 중 순수 함수 사용의 장점이 아닌 것은 무엇인가?

> [] They are easier to analyze
>
> [] They are easier to run in parallel
>
> [x] `They are easier to write`

<br>

<br>