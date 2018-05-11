---
layout: post
title: "SoloLearn 번역 - 06. Functions as Objects (Function & Modules)"
categories: dev
tags: python
---

## Functions (함수)

- Although they are created differently from normal variables, **functions** are just like any other kind of value.
  - 그것들은 일반적인 변수와 다르게 생성되지만, **함수**는 다른 어떤 종류의 값과 같다.
- They can be assigned and reassigned to variables, and later referenced by those names.
  - 그것들은 변수를 할당하고, 변수에 다시 할당할 수 있으며, 나중에 해당 이름으로 참조할 수 있다.

```python
def multiply(x, y):
   return x * y

a = 4
b = 7
operation = multiply
print(operation(a, b))
```

<br>

- Result:

```python
>>>
28
>>>
```

<br>

> The example above assigned the function **multiply** to a variable **operation**.
>
> 위의 예제는 변수 **operation**에 **multiply** 함수를 할당했다.

> Now, the name **operation** can also be used to call the function.
>
> 이제, 이름 **operation**을 사용해서 함수를 호출할 수도 있다.

------

<br>

## Functions 02

- Functions can also be used as **arguments** of other functions.
  - 함수는 다른 함수의 **인수**로도 사용할 수 있다.

```python
def add(x, y):
   return x + y

def do_twice(func, x, y):
   return func(func(x, y), func(x, y))

a = 5
b = 10

print(do_twice(add, a, b))
```

<br>

- Result:

```python
>>>
30
>>>
```

<br>

> As you can see, the function **do_twice** takes a function as its argument and calls it in its body.
>
> 보다시피, **do_twice** 함수는 함수를 인수로 취해서 본문에서 호출한다.

------

<br>

## QUIZ

- What is the output of this code?
  - speak!
  - word!
  - **shout!**

```python
def shout(word):
   return word + "!"
speak = shout
output = speak("shout")
print(output)
```

<br>

- Fill in the blanks to pass the function "square" as an argument to the function "test":

```python
def square(x):
   return x * x

def test(func, x):
   print(func(x))
   
test(square, 42)
```

<br>