---
layout: post
title: "(Basics 10) 변수"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- `Variables` play a very important role in most programming languages, and Python is no exception.
  - `변수`는 대부분의 프로그래밍 언어에서 아주 중요한 역할을 한다.
  - Python도 예외가 아니다.
- A variable allows you to store a value by assigning it to a name, which can be used to refer to the value later in the program.
  - 변수를 사용하면, 이름에 값을 할당해서 저장할 수 있다.
  - 이 이름은 나중에 프로그램에서 값을 참조하는 데 사용될 수 있다.
- To assign a variable, use `one equals sign`.
  - 변수를 할당하기 위해, `하나의 등호 (=)`를 사용한다.
- Unlike most lines of code we've looked at so far, it doesn't produce any output at the Python console.
  - 지금까지 살펴본 대부분의 코드들과 달리, Python 콘솔에서 출력을 생성하지 않는다.

```python
>>> x = 7
>>> print(x)
# 7

>>> print(x + 3)
# 10

>>> print(x)
# 7
```

[코드 실행 확인](https://code.sololearn.com/288/#py)

<br>

> You can use variables to perform corresponding operations, just as you did with numbers and strings.
>
> 숫자와 문자열에서 했던 것처럼, 변수를 사용해서 해당 연산을 수행할 수 있다.
>
> As you can see, the variable stores its value throughout the program.
>
> 보다시피, 변수는 프로그램 전체에서 값을 저장한다.

<br>

- Variables can be reassigned as many times as you want, in order to change their value.
  - 변수 값을 변경하기 위해 원하는 만큼 변수를 재할당할 수 있다.
- In Python, variables don't have specific types, so you can assign a string to a variable, and later assign an integer to the same variable.
  - 변수에 특정 타입이 없으므로 문자열을 변수에 할당한 다음, 나중에 동일한 변수에 정수를 할당할 수 있다.

```python
>>> x = 123.456
>>> print(x)
# 123.456

>>> x = "This is a string"
>>> print(x + "!")
# This is a string!
```

[코드 실행 확인](https://code.sololearn.com/289/#py)

<br>

> However, it is not good practice.
>
> 하지만 좋은 습관이 아니다.
>
> To avoid mistakes, try to avoid overwriting the same variable with different data types.
>
> 실수를 피하기 위해, 동일한 변수에 다른 데이터 타입으로 덮어쓰지 않는다.

<br>

<br>

## Variable Names

###### 변수 이름

<br>

- Certain restrictions apply in regard to the characters that may be used in Python variable names.
  - Python 변수 이름에 사용될 수 있는 글자에 관해서 특정 제한이 적용된다.
- The only characters that are allowed are letters, numbers, and underscores.
  - 문자, 숫자, 밑줄만 허용된다.
- Not following these rules results in errors.
  - 이 규칙들을 따르지 않으면 에러가 발생한다.

```python
>>> this_is_a_normal_name = 7

>>> 123abc = 7
# SyntaxError: invalid syntax

>>> spaces are not allowed
# SyntaxError: invalid syntax
```

[코드 실행 확인](https://code.sololearn.com/290/#py)

<br>

> Python is a case sensitive programming language.
>
> Python은 대소문자를 구분하는 프로그래밍 언어이다.
>
> Thus, `Lastname` and `lastname` are two different variable names in Python.
>
> 따라서 Python에서 `Lastname`과 `lastname`은 서로 다른 변수 이름이다.

<br>

<br>

#### Variable

###### 변수

- Trying to reference a variable you haven't assigned to causes an `error`.
  - 할당하지 않은 변수를 참조하려고 하면, `에러`가 발생한다.
- You can use the `del` statement to remove a variable, which means the reference from the name to the value is deleted, and trying to use the variable causes an error.
  - `del` 문을 사용해서 변수를 제거할 수 있다.
  - 이름에서 값에 대한 참조가 제거되고, 변수를 사용하려고 하면 에러가 발생한다.
- Deleted variables can be reassigned to later as normal.
  - 제거된 변수는 나중에 정상적으로 재할당할 수 있다.

```python
>>> foo = "a string"
>>> foo
# a string

>>> bar
# NameError: name 'bar' is not defined

>>> del foo
>>> foo
# NameError: name 'foo' is not defined
```

<br>

- You can also take the value of the variable from the user input.
  - 사용자 입력에서 변수의 값을 가져올 수도 있다.

```python
>>> foo = input("Enter a number: ")
>>> print(foo)
# Enter a number: 8
# 8
```

[코드 실행 확인](https://code.sololearn.com/949/#py)

<br>

> The variables `foo` and `bar` are called `metasyntactic` variables, meaning that they are used as placeholder names in example code to demonstrate something.
>
> 변수 `foo`와 `bar`를 `metasyntactic` 변수라고 한다.
>
> 예제 코드에서 placeholder 이름으로 사용되어 무언가를 보여준다.
>
> `placeholder`: 텍스트 필드에 무엇을 입력해야 할 지 알려주는 역할을 한다.

<br>

<br>

#### QUIZ

- What is the output of this code?
  - 아래 코드의 출력은 무엇인가?

```python
>>> spam = "eggs"
>>> print(spam * 3)
```

> `eggseggseggs`

<br>

- Which of these is a valid variable name in Python?
  - 다음 중 Python에서 유효한 변수 이름은 무엇인가?

> [] a-variable-name
>
> [] a variable name
>
> [x] `A_VARIABLE_NAME`

<br>

- What is the output of this code?
  - 아래 코드의 출력은 무엇인가?

```python
>>> spam = 2
>>> eggs = 3
>>> del spam
>>> eggs = 4
>>> spam = 5
>>> print(spam * eggs)
```

> `20`

<br>

<br>