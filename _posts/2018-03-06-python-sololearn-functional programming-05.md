---
layout: post
title: "SoloLearn 번역 - 05. Decorators (Functional Programming)"
categories: dev
tags: python
---

## Decorators

- **Decorators** provide a way to modify functions using other functions.
  - **Decorators**는 다른 함수를 사용해서 함수를 수정하는 방법을 제공한다.
  - `decorator`: a function that modifies another function or method (다른 함수 또는 메소드를 수정하는 함수)
- This is ideal when you need to extend the functionality of functions that you don't want to modify.
  - 이는 수정하고 싶지 않은 함수의 상관관계를 확장해야 할 때 이상적이다.

<br>

- Example:

```python
def decor(func):
   def wrap():
      print("============")
      func()
      print("============")
	return wrap

def print_text():
   print("Hello world!")
   
decorated = decor(print_text)
decorated()
```

<br>

- We defined a function named **decor** that has a single parameter **func**.
  - 우리는 하나의 매개변수 **func**가 있는 **decor**라는 함수를 정의했다.
- Inside **decor**, we defined a nested function named **wrap**.
  - **decor** 안에는, **wrap**이라는 중첩된 함수를 정의했다.
- The **wrap** function will print a string, then call **func()**, and print another string.
  - **wrap** 함수는 문자열을 출력한 다음, **func()**를 호출하고, 다른 문자열을 출력한다.
- The **decor** function returns the **wrap** function as its result.
  - **decor** 함수는 결과로 **wrap** 함수를 반환한다.
- We could say that the variable **decorated** is a decorated version of **print_text** - it's **print_text** plus something.
  - **decorated** 변수가 decorated 버전의 **print_text**라고 말할 수 있다. 이것은 무언가와 더한 **print_text**이다.
- In fact, if we wrote a useful decorator we might want to replace **print_text** with the decorated version altogether so we always got our "plus something" version of **print_text**.
  - 실제로 유용한 decorator를 작성했다면, **print_text**를 decorated 버전으로 대체해서, 항상 "무언가를 더한" 버전의 **print_text**를 얻을 수 있다.
- This is done by re-assigning the variable that contains our function:
  - 이것은 우리 함수를 포함하는 변수를 다시 할당함으로써 이루어진다.

```python
print_text = decor(print_text)
print_text()
```

<br>

> Now **print_text** corresponds to our decorated version.
>
> 이제 **print_text**는 decorated 버전과 일치한다.

------

<br>

## Decorators 02

- In our previous example, we decorated our function by replacing the variable containing the function with a wrapped version.
  - 앞의 예제에서, 함수를 포함하는 변수를 wrapped 버전으로 대체해서 함수를 decorated 했다.

```python
def print_text():
   print("Hello world!")
   
print_text = decor(print_text)
```

<br>

- This pattern can be used at any time, to wrap any function.
  - 이 패턴은 언제든지 사용할 수 있고, 모든 함수를 wrap 할 수 있다.
- Python provides support to wrap a function in a decorator by pre-pending the function definition with a decorator name and the @ symbol.
  - Python은 함수 정의를 decorator 이름과 @ 기호로 미리 decorator에 wrap하는 함수를 제공한다.
- If we are defining a function we can "decorate" it with the @ symbol like:
  - 만약 함수를 정의한다면, 다음과 같이 @ 기호로 "decorate" 할 수 있다.

```python
@decor
def print_text():
   print("Hello world!")
```

<br>

- This will have the same result as the above code.
  - 위의 코드와 같은 결과가 된다.

<br>

> A single function can have multiple decorators.
>
> 하나의 함수는 여러 개의 decorator를 가질 수 있다.

------

<br>

## QUIZ

- What are decorators?
  - **Functions that modify other functions**
  - Functions that return themselves
  - Functions with an at sign in their names

<br>

- Which statement can be used to achieve the same behavior as my_func = my_dec(my_func)?
  - my_func = @my_dec
  - my_dec(my_func)
  - @my_dec

<br>