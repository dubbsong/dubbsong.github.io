---
layout: post
title: "SoloLearn 번역 - 04. Generators (Functional Programming)"
categories: dev
tags: python
---

## Generators (생성자)

- **Generators** are a type of iterable, like lists or tuples.
  - **생성자**는 배열과 튜플 같은 iterable 타입이다.
- Unlike lists, they don't allow indexing with arbitrary indices, but they can still be iterated through with **for** loops.
  - 배열과 달리, 임의의 인덱스를 사용해서 인덱싱을 허용하지 않지만, **for** 루프를 사용해서 반복할 수 있다.
- They can be created using functions and the yield statement.
  - 함수와 yield 문을 사용해서 생성될 수 있다.
  - `yield`: returns a value from a generator function

<br>

- Example:

```python
def countdown():
   i = 5
   while i > 0:
      yield i
      i -= 1
      
for i in countdown():
   print(i)
```

<br>

- Result:

```python
>>>
5
4
3
2
1
```

<br>

> The **yield** statement is used to define a generator, replacing the return of a function to provide a result to its caller without destroying local variables.
>
> **yield** 문은 생성자를 정의하는 데 사용되고, 함수의 반환을 대체해서 로컬 변수를 파괴하지 않고 호출자에게 결과를 제공한다.

------

<br>

## Generators 02

- Due to the fact that they yield one item at a time, generators don't have the memory restrictions of lists.
  - 한 번에 하나의 항목을 산출한다는 사실 때문에, 생성자에는 배열에 대한 메모리 제한이 없다.
- In fact, they can be **infinite!**
  - 사실, 생성자는 무한할 수 있다.

```python
def infinite_sevens():
   while True:
      yield 7
      
for i in infinite_sevens():
   print(i)
```

<br>

- Result:

```python
>>>
7
7
7
7
7
7
7
...
```

<br>

> In short, **generators** allow you to declare a function that behaves like an iterator, i.e. it can be used in a **for** loop.
>
> 즉, **생성자**를 사용하면 반복자처럼 동작하는 함수를 선언할 수 있다. 즉, for 루프에서 사용할 수 있다.

------

<br>

## Generators 03

- Finite generators can be converted into lists by passing them as arguments to the **list** function.
  - 유한 생성자는 **배열** 함수에 인수로 전달해서 배열로 변환될 수 있다.

```python
def numbers(x):
   for i in range(x):
      if i % 2 == 0:
         yield i
         
print(list(numbers(11)))
```

<br>

- Result:

```python
>>>
[0, 2, 4, 6, 8, 10]
>>>
```

<br>

> Using **generators** results in improved performance, which is the result of the lazy (on demand) generation of value, which translates to lower memory usage.
>
> **생성자**를 사용하면 성능이 향상된다. 이는 게으른 값의 생성 결과로, 메모리 사용량이 줄어든다.

> Furthermore, we do not need to wait until all the elements have been generated before we start to use them.
>
> 뿐만 아니라, 모든 요소가 사용되기 전에 생성될 때까지 기다릴 필요가 없다.

------

<br>

## QUIZ

- What statement is used in functions to turn them into generators?
  - return
  - generate
  - **yield**

<br>

- Fill in the blanks to create a prime number generator, that yields all prime numbers in a loop. (Consider having an is_prime function already defined):

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
  - "spam"
  - **['s', 'sp', 'spa', 'spam']**
  - ['spam', 'spam', 'spam', 'spam']

```python
def make_word():
   word = ""
   for ch in "spam":
      word += ch
      yield word
      
print(list(make_word()))
```

<br>