---
layout: post
title: "(Functional Programming 04) Generators"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- `Generators` are a type of iterable, like lists or tuples.
  - `Generator`는 리스트나 튜플과 같은 iterable 타입이다.
- Unlike lists, they don't allow indexing with arbitrary indices, but they can still be iterated through with `for` loops.
  - 리스트와 달리, 임의의 색인을 사용해서 인덱싱 할 수 없지만, `for` loop를 사용해서 반복할 수 있다.
- They can be created using functions and the `yield` statement.
  - 함수와 `yield` 문을 사용해서 생성할 수 있다.

```python
def countdown():
  i = 5
  
  while i > 0:
    yield i
    i -= i
    
for i in countdown():
  print(i)
  
# 5
# 4
# 3
# 2
# 1
```

[코드 실행 확인](https://code.sololearn.com/388/#py)

<br>

> The `yield` statement is used to define a generator, replacing the return of a function to provide a result to its caller without destroying local variables.
>
> `yield` 문은 generator를 정의하는 데 사용된다.
>
> 함수의 반환을 대체해서 로컬 변수를 파괴하지 않고 호출자에게 결과를 제공한다.

<br>

- Due to the fact that they `yield` one item at a time, generators don't have the memory restrictions of lists.
  - 한 번에 하나의 item을 `yield`한다는 사실 때문에, generator는 리스트의 메모리 제한이 없다.
- In fact, they can be infinite.
  - 사실 무한할 수 있다.

```python
def infinite_sevens():
  while True:
    yield 7
    
for i in infinite_sevens():
  print(i)
  
# 7
# 7
# ...
```

<br>

> In short, `generators` allow you to declare a function that behaves like an iterator, i.e. it can be used in a `for` loop.
>
> 간단히 말해, `generator`를 사용하면 반복자처럼 동작하는 함수, 즉 `for` loop에서 사용할 수 있는 함수를 선언할 수 있다.

<br>

- Finite generators can be converted into lists by passing them as arguments to the `list` function.
  - 유한 generator는, `list` 함수에 인수로 전달해서 리스트로 변환될 수 있다.

```python
def numbers(x):
  for i in range(x):
    if i % 2 == 0:
      yield i
      
print(list(numbers[11]))
# [0, 2, 4, 6, 8, 10]
```

[코드 실행 확인](https://code.sololearn.com/390/#py)

<br>

> Using `generators` results in improved performance, which is the result of the lazy (on demand) generation of values, which translates to lower memory usage.
>
> `generator`를 사용하면 성능이 향상된다.
>
> 이는 값을 느리게(사용자의 요구에 따라 필요한 정보를 제공) 생성해서 메모리 사용량을 줄인다.
>
> Furthermore, we do not need to wait until all the elements have been generated before we start to use them.
>
> 또한, 사용하기 전에 모든 엘리먼트가 생성될 때까지 기다릴 필요가 없다.

<br>

<br>

#### QUIZ

- What statement is used in functions to turn them into generators?
  - 함수에서 generator로 변경하는 데 사용되는 명령문은 무엇인가?

> `yield`

<br>

- Fill in the blanks to create a prime number generator, that yields all prime numbers in a loop. (Consider having an is_prime function already defined)
  - loop에서 모든 소수를 yield하는 소수 generator를 생성해라.
  - (is_prime 함수가 이미 정의되어 있다)

```python
def get_primes():
  num = 2
  
  while True:
    if is_prime(num):
      yield num
    num += 1
```

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
def make_word():
  word = ""
  
  for ch in  "spam":
    word += ch
    yield word
    
print(list(make_word()))
```

> `['s', 'sp', 'spa', 'spam']`

<br>

<br>