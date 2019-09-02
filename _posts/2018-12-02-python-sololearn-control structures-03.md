---
layout: post
title: "(Control Structures 03) else 문"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- An `else` statement follows an `if` statement, and contains code that is called when the if statement evaluates to `False`.
  - `else` 문은 `if` 문 뒤에 온다.
  - `if` 문이 `False`로 평가될 때 호출되는 코드를 포함한다.
- As with `if` statements, the code inside the block should be indented.
  - `if` 문과 마찬가지로, 블록 내부의 코드는 들여쓰기 해야 한다.

```python
x = 4

if x == 5:
  print("Yes")
else:
  print("No")
  
# No
```

[코드 실행 확인](https://code.sololearn.com/300/#py)

<br>

- You can chain `if` and `else` statements to determine which option in a series of possibilities is true.
  - `if`와 `else` 문을 연결해서, 어떤 옵션이 참(true)인지 결정할 수 있다.

```python
num = 7

if num == 5:
  print("Number is 5")
else:
  if num == 11:
    print("Number is 11")
  else:
    if num == 7:
      print("Number is 7")
    else:
      print("Number isn't 5, 11 or 7")
      
# Number is 7
```

[코드 실행 확인](https://code.sololearn.com/301/#py)

<br>

## elif Statements

###### elif 문

<br>

- The `elif` (short for else if) statement is a shortcut to use when chaining `if` and `else` statements.
  - `elif` (else if의 단축)문은 `if`와 `else` 문을 열결할 때 사용하는 단축이다.
- A series of `if elif` statements can have a final `else` block, which is called if none of the `if` or `elif` expressions is True.
  - 일련의 `if elif` 문은 최종 `else` 블록을 가질 수 있다.
  - `if` 또는 `elif` 표현식 중 어느 것도 참(True)이 아닌 경우 호출된다.

```python
num == 7

if num == 5:
  print("Number is 5")
elif num == 11:
  print("Number is 11")
elif num == 7:
  print("Number is 7")
else:
  print("Number isn't 5, 11 or 7")
  
# Number is 7
```

[코드 실행 확인](https://code.sololearn.com/302/#py)

<br>

> In other programming languages, equivalents to the `elif` statement have varying names, including `else if`, `elseif` or `elsif`.
>
> 다른 프로그래밍 언어에서 `elif` 문과 동일한 것으로 `else if`, `elseif`, `elsif`가 있다.

<br>

<br>

#### QUIZ

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
if 1 + 1 == 2:
  if 2 * 2 == 8:
    print("if")
  else:
    print("else")
```

> `else`

<br>

- A shorter option for an "else if" statement is:
  - "else if" 문의 단축은 무엇인가?

> `elif`

<br>

<br>