---
layout: post
title: "SoloLearn - 03. Function Arguments (Function & Modules)"
categories: dev
tags: python
---

## Arguments (인수)

- All the function definitions we've looked at so far have been functions of zero arguments, which are called with empty parentheses.
  - 지금까지 살펴본 모든 함수 정의는 빈 괄호로 호출되는 0 인수의 함수이다.
- However, most functions take arguments.
  - 하지만, 대부분의 함수는 인수를 취한다.
- The example below defines a function that takes one argument:
  - 아래의 예제는 하나의 인수를 취하는 함수를 정의한다.

```python
def print_with_exclamation(word):
   print(word + "!")
   
print_with_exclamation("spam")
print_with_exclamation("eggs")
print_with_exclamation("python")
```

<br>

- Result:

```python
>>>
spam!
eggs!
python!
>>>
```

<br>

> As you can see, the argument is defined inside the parentheses.
>
> 보다시피, 인수는 괄호 안에 정의되어 있다.

<br>

## Arguments 02

- You can also define functions with more than one argument; separate them with commas.
  - 하나 이상의 인수가 있는 함수도 정의할 수 있다; 인수들을 쉼표로 구분해라.

```python
def print_sum_twice(x, y):
   print(x + y)
   print(x + y)
   
print_sum_twice(5, 8)
```

<br>

- Result:

```python
>>>
13
13
>>>
```

<br>

## Arguments 03

- Function arguments can be used as variables inside the function definition.
  - 함수 인수는 함수 정의 내에서 변수로 사용할 수 있다.
- However, they cannot be referenced outside of the function's definition.
  - 하지만, 함수의 정의 외부에서는 참조할 수 없다.
- This also applies to other variables created inside a function.
  - 이는 함수 내부에서 생성된 다른 변수에도 적용된다.

```python
def function(variable):
   variable += 1
   print(variable)
   
function(7)
print(variable)
```

<br>

- Result:

```python
>>>
8

NameError: name 'variable' is not defined
>>>
```

<br>

> Technically, **parameters** are the variables in a function definition, and **arguments** are the values put into parameters when functions are called.
>
> 기술적으로, **매개변수**는 함수 정의 내의 변수이며, **인수**는 함수가 호출될 때 매개변수에 입력되는 값이다.

<br>

## QUIZ

- What is the result of this code?

```python
def print_double(x):
   print(2 * x)
   
print_double(3)


6
```

<br>

- Fill in the blanks to define a function that takes two arguments and prints their multiplication.

```python
def print_mult(x, y):
   print(x * y)
```

<br>

- Fill in the blanks to define a function that prints "Yes", if its parameter is an even number, and "No" otherwise.

```python
def even(x):
   if x%2 == 0:
      print("Yes")
	else:
   	print("No")
```

<br>