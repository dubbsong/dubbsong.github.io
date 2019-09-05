---
layout: post
title: "(Functions & Modules 06) 객체로서의 함수"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

## Functions

###### 함수

<br>

- Although they are created differently from normal variables, `functions` are just like any other kind of value.
  - 일반 변수와 다르게 생성되지만, `함수`는 다른 종류의 값과 같다.
- They can be assigned and reassigned to variables, and later referenced by those names.
  - 변수에 할당과 재할당을 할 수 있다.
  - 그리고 나중에 해당 이름으로 참조할 수 있다.

```python
def multiply(x, y):
  return x * y

a = 4
b = 7
operation = multiply
print(operation(a, b))
# 28
```

[코드 실행 확인](https://code.sololearn.com/338/#py)

<br>

> The example above assigned the function `multiply` to a variable `operation`.
>
> 위의 예제는 변수 `operation`에 함수 `multiply`를 할당했다.
>
> Now, the name `operation` can also be used to call the function.
>
> 이제 함수를 호출하는 데 `operation`도 사용할 수 있다.

<br>

- Functions can also be used as `arguments` of other functions.
  - 함수는 다른 함수의 `인수`로도 사용될 수 있다.

```python
def add(x, y):
  return x + y

def do_twice(func, x, y):
  return func(func(x, y), func(x, y))

a = 5
b = 10

print(do_twice(add, a, b))
# 30
```

[코드 실행 확인](https://code.sololearn.com/339/#py)

<br>

> As you can see, the function `do_twice` takes a function as its argument and calls it in its body.
>
> 보다시피, `do_twice` 함수는 함수를 인수로 받아 body에서 호출한다.

<br>

<br>

#### QUIZ

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
def shout(word):
  return word + "!"

speak = shout
output = speak("shout")
print(output)
```

> `shout!`

<br>

- Fill in the blanks to pass the function "square" as an argument to the function "test":
  - "square" 함수를 "test" 함수의 인수로 전달해라.

```python
def square(x):
  return x * x

def test(func, x):
  print(func(x))
  
test(square, 42)
```

<br>

<br>