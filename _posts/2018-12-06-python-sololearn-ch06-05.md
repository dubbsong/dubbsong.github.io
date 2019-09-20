---
layout: post
title: "(Functional Programming 05) 데코레이터(Decorator)"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- `Decorators` provide a way to modify functions using other functions.
  - `데코레이터`는 다른 함수를 사용해서 함수를 수정하는 방법을 제공한다.
- This is ideal when you need to extend the functionality of functions that you don't want to modify.
  - 이는 수정하지 않으려는 기능을 확장해야 할 때 이상적이다.

```python
def decor(func):
  def wrap():
    print("===========")
    func()
    print("===========")
  return wrap

def print_text():
  print("Hello World")
  
decorated = decor(print_text)
decorated()

# ===========
# Hello World
# ===========
```

[코드 실행 확인](https://code.sololearn.com/391/#py)

<br>

- We defined a function named `decor` that has a single parameter `func`.
  - 하나의 매개변수 `func`가 있는 `decor`라는 함수를 정의했다.
- Inside `decor`, we defined a nested function named `wrap`.
  - `decor` 내에서, `wrap`이라는 중첩 함수를 정의했다.
- The `wrap` function will print a string, then call `func()`, and print another string.
  - `wrap` 함수는 문자열을 출력한 다음, `func()`를 호출하고, 다른 문자열을 출력한다.
- The `decor` function returns the `wrap` function as its result.
  - `decor` 함수는 `wrap` 함수를 결과로 반환한다.
- We could say that the variable `decorated` is a decorated version of `print_text` \- it's `print_text` plus something.
  - `decorated` 변수는 `print_text`의 장식된 버전이라고 말할 수 있다.
  - `print_text`에 무언가를 더한 것이다.

<br>

- In fact, if we wrote a useful decorator we might want to replace `print_text` with the decorated version altogether so we always got our "plus something" version of `print_text`.
  - `print_text`를 대체하기 위해 유용한 데코레이터를 작성했다면, `print_text`의 "무언가 더한" 버전을 항상 얻을 수 있다.
- This is done by re\-assigning the variable that contains our function:
  - 이는 함수가 포함된 변수를 다시 할당해서 수행된다.

<br>

- In our previous example, we decorated our function by replacing the variable containing the function with a wrapped version.
  - 이전 예제에서, 함수를 포함하는 변수를 wrapped 버전으로 대체해서 함수를 장식했다.

```python
def print_text():
  print("Hello World")
  
print_text = decor(print_text)
```

[코드 실행 확인](https://code.sololearn.com/393/#py)

<br>

- This pattern can be used at any time, to wrap any function.
  - 이 패턴은 언제든지 함수를 wrap 할 수 있다.
- Python provides support to wrap a function in a decorator by pre\-pending the function definition with a decorator name and the @ symbol.
  - Python은 데코레이터에서 함수를 wrap하는 것을 지원한다.
  - 데코레이터 이름과 @ 기호를 함수 정의 앞에 붙인다.
- If we are defining a function we can "decorate" it with the @ symbol like:
  - 함수를 정의하는 경우, 다음과 같이 @ 기호로 함수를 "decorate" 할 수 있다.

```python
@decor
def print_text():
  print("Hello World")
```

[코드 실행 확인](https://code.sololearn.com/394/#py)

<br>

- This will have the same result as the above code.
  - 위의 코드와 동일한 결과가 나타난다.

<br>

> A single function can have multiple decorators.
>
> 하나의 함수는 여러 데코레이터를 가질 수 있다.

<br>

<br>

#### QUIZ

- What are decorators?
  - 데코레이터는 무엇인가?

> Functions that modify other functions
>
> 다른 함수를 수정하는 함수

<br>

- Which statement can be used to achieve the same behavior as my\_func = my\_dec(my\_func)?
  - my\_func = my\_dec(my\_func)와 동일한 동작을 달성하기 위해 사용할 수 있는 명령문은 무엇인가?

> `@my_dec`

<br>

<br>