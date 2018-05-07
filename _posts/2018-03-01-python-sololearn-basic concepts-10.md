---
layout: post
title: "SoloLearn - 10. Variables (basic concepts)"
categories: dev
tags: python
---

## Variables (변수)

- **Variables** play a very important role in most programming languages, and Python is no exception.
  - **변수**는 대부분의 프로그래밍 언어에서 매우 중요한 역할을 하고, Python도 예외는 아니다.
- A `variable` allows you to store a value by assigning it to a name, which can be used to refer to the value later in the program.
  - 변수는 이름에 값을 할당해서 저장할 수 있다. 이 값은 나중에 프로그램에서 값을 참조하는 데 사용할 수 있다.

<br>

- To assign a variable, use **one equals sign**.
  - 변수를 할당하려면, **등호 하나**를 사용해라.
- Unlike most lines of code we've looked at so far, it doesn't produce any output at the Python console.
  - 지금까지 살펴 본 대부분의 코드와 달리, Python 콘솔에서 아무 출력도 하지 않는다.

```python
>>> x = 7
>>> print(x)
7

>>> print(x + 3)
10

>>> print(x)
7
```

<br>

> You can use variables to perform corresponding operations, just as you did with numbers and strings.
>
> 숫자와 문자열로 했던 것처럼, 변수를 사용해서 해당 작업을 수행할 수 있다.

> As you can see, the variable stores its value throughout the program.
>
> 보다시피, 변수는 프로그램 전체에 걸쳐 값을 저장한다.

------

<br>

## Variables 02

- Variables can be reassigned as many times as you want, in order to change their value.
  - 변수는 값을 변경하기 위해 원하는 만큼 재할당 할 수 있다.
- In Python, variables don't have specific types, so you can assign a string to a variable, and later assign an integer to the same variable.
  - Python에서는, 변수에 특정 타입이 없으므로, 변수에 문자열을 할당하고, 나중에 동일한 변수에 정수를 할당할 수 있다.

```python
>>> x = 123.456
>>> print(x)
123.456

>>> x="This is a string"
>>> print(x + "!")
This is a string!
```

------

<br>

## Variable Names

- Certain restrictions apply in regard to the characters that may be used in Python variable names.
  - Python 변수 이름에서 사용할 수 있는 문자와 관련하여 특정 제한이 적용된다.
- The only characters that are allowed are letters, numbers, and underscores.
  - 허용되는 문자는 문자, 숫자, 밑줄뿐이다.
- Also, they can't start with numbers.
  - 또한, 숫자로 시작할 수 없다.
- Not following these rules results in errors.
  - 이러한 규칙을 따르지 않으면 에러가 발생한다.

```python
>>> this_is_a_normal_name = 7

>>> 123abc = 7
SyntaxError: invalid syntax

>>> spaces are not allowed
SyntaxError: invalid syntax
```

<br>

> Python is a case sensitive programming language.
>
> Python은 대소문자를 구분하는 프로그래밍 언어이다.

> Thus, **Lastname** and **lastname** are two different variable names in Python.
>
> 따라서, **Lastname**과 **lastname**은 Python에서 두 개의 다른 변수 이름이다.

------

<br>

## Variables 03

- Trying to reference a variable you haven't assigned to causes an **error**.
  - 할당하지 않은 변수를 참조하려고 시도하면, **에러**가 발생한다.
- You can use the **del** statement to remove a variable, which means the reference from the name to the value is deleted, and trying to use the variable causes an error.
  - **del** 문을 사용해서 변수를 제거할 수 있다. 즉, 이름에서 값으로의 참조가 삭제되고, 변수를 사용하려고 시도하면, 에러가 발생한다.
- Deleted variables can be reassigned to later as normal.
  - 삭제된 변수는 나중에 정상적으로 재할당 할 수 있다.

```python
>>> foo = "a string"
>>> foo
'a string'

>>> bar
NameError: name 'bar' is not defined

>>> del foo
>>> foo
NameError: name 'foo' is not defined
```

<br>

- You can also take the value of the variable from the user input.
  - 유저 입력에서 변수 값을 가져올 수도 있다.

```python
>>> foo = input("Enter a number: ")
Enter a number: 7

>>> print(foo)
7
```

<br>

> The variables **foo** and **bar** are called **metasyntactic** variables, meaning that they are used as placeholder names in example code to demonstrate something.
>
> 변수 **foo**와 **bar**는 **metasyntactic** 변수로 불린다. 이는 무언가를 보여주기 위해 예제 코드에서 placeholder 이름으로 사용된다는 것을 의미한다.

------

<br>

## QUIZ

- What is the output of this code?

```python
>>> spam = "eggs"
>>> print(spam * 3)
eggseggseggs
```

<br>

- Drag the correct answer to make the code work correctly.

```python
>>> x = 5
>>> y = 7
>>> print(x + y)
12
```

<br>

- Which of these is a valid variable name in Python?
  - a-variable-name
  - a variable name
  - **A_VARIABLE_NAME**

<br>

- What is the output of this code?

```python
>>> spam = 2
>>> eggs = 3
>>> del spam
>>> eggs = 4
>>> spam = 5
>>> print(spam * eggs)
20
```

<br>