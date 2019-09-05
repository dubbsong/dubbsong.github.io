---
layout: post
title: "(Functions & Modules 03) 함수 인수"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- All the function definitions we've looked at so far have been functions of zero arguments, which are called with empty parentheses.
  - 지금까지 살펴본 모든 함수 정의는, 빈 괄호로 호출되는 인수가 없는 함수였다.
- However, most functions take arguments.
  - 하지만 대부분의 함수는 인수를 사용한다.
- The example below defines a function that takes one argument:
  - 아래 예제는 하나의 인수를 사용하는 함수를 정의한다.

```python
def print_with_exclamation(word):
  print(word + "!")
  
print_with_exclamation("spam")
print_with_exclamation("eggs")

# spam!
# eggs!
```

[코드 실행 확인](https://code.sololearn.com/331/#py)

<br>

> As you can see, the argument is defined inside the parentheses.
>
> 보다시피, 인수는 괄호 내에 정의된다.

<br>

- You can also define functions with more than one argument; separate them with commas.
  - 둘 이상의 인수로 함수를 정의할 수도 있다.
  - 쉼표로 구분한다.

```python
def print_sum_twice(x, y):
  print(x + y)
  print(x + y)
  
print_sum_twice(5, 8)

# 13
# 13
```

[코드 실행 확인](https://code.sololearn.com/332/#py)

<br>

- Function arguments can be used as variables inside the function definition.
  - 함수 인수는 함수 정의 내에서 변수로 사용될 수 있다.
- However, they cannot be referenced outside of the function's definition.
  - 하지만 함수의 정의 외부에서는 참조할 수 없다.
- This also applies to other variables created inside a function.
  - 이는 함수 내에서 생성된 다른 변수에도 적용된다.

```python
def function(variable):
  variable += 1
  print(variable)
  
function(7)
# 8

print(variable)
# NameError: name 'variable' is not defined
```

[코드 실행 확인](https://code.sololearn.com/333/#py)

<br>

> Technically, `parameters` are the variables in a function definition, and `arguments` are the values put into parameters when functions are called.
>
> 기술적으로, `매개변수`는 함수 정의의 변수이다.
>
> `인수`는 함수가 호출될 때 매개변수에 입력된 값이다.

<br>

<br>

#### QUIZ

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
def print_double(x):
  print(2 * x)
  
print_double(3)
```

> `6`

<br>

- Fill in the blanks to define a function that takes two arguments and prints their multiplication.
  - 두 개의 인수를 사용해서 곱셈을 출력하는 함수를 정의해라.

```python
def print_mult(x, y):
  print(x * y)
```

<br>

- Fill in the blanks to define a function that prints "Yes", if its parameter is an even number, and "No" otherwise.
  - 매개변수가 짝수인 경우 "Yes"를 출력하고, 홀수인 경우 "No"를 출력하는 함수를 정의해라.

```python
def even(x):
  if x % 2 == 0:
    print("Yes")
  else:
    print("No")
```

<br>

<br>