---
layout: post
title: "(Control Structures 02) if 문"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- You can use `if` statements to run code if a certain condition holds.
  - 특정 조건이 유지되는 경우, `if` 문을 사용해서 코드를 실행할 수 있다.
- If an expression evaluates to `True`, some statements are carried out.
  - 표현식이 `True`로 평가되면, 명령문이 실행된다.
- Otherwise, they aren't carried out.
  - 표현식이 `False`로 평가되면, 실행되지 않는다.
- An if statement looks like this:
  - if 문은 다음과 같다.

```python
if expression:
  statements
```

<br>

> Python uses `indentation` (white space at the beginning of a line) to delimit blocks of code.
>
> Python은 `들여쓰기`(줄 시작의 공백)를 사용해서 코드 블록을 구분한다.
>
> Other languages, such as C, use curly braces to accomplish this, but in Python indentation is mandatory; programs won't work without it.
>
> C와 같은 다른 언어는 이를 위해 중괄호를 사용하지만, Python에서는 들여쓰기가 필수이다.
>
> 그렇지 않으면 프로그램이 작동하지 않는다.

<br>

- Here is an example `if` statement:
  - 다음은 `if` 문의 예제이다.

```python
if 10 > 5:
  print("10 greater than 5")
  
print("Program ended")

# 10 greater than 5
# Program ended
```

[코드 실행 확인](https://code.sololearn.com/298/#py)

<br>

- The expression determines whether 10 is greater than five.
  - 위의 표현식은 10이 5보다 큰지를 결정한다.
- Since it is, the indented statement runs, and "10 greater than 5" is output.
  - 10이 5보다 크기 때문에, 들여쓰기된 명령문이 실행된다.
- Then, the unindented statement, which is not part of the `if` statement, is run, and "Program ended" is displayed.
  - 그런 다음, `if` 문의 일부가 아닌 들여쓰기되지 않은 명령문이 실행된다.

<br>

- Notice the `colon` at the end of the expression in the `if` statement.
  - `if` 문에서 표현식의 끝에 있는 `콜론`(:)에 주의한다.

<br>

> As the program contains multiple lines of code, you should create it as a separate file and run it.
>
> 프로그램에 여러 줄의 코드가 포함되어 있으므로, 별도의 파일로 생성해서 실행해야 한다.

<br>

- To perform more complex checks, `if` statements can be nested, one inside the other.
  - 보다 복잡한 검사를 수행하기 위해, `if` 문을 중첩할 수 있다.
- This means that the inner `if` statement is the statement part of the outer one.
  - 즉 내부 `if` 문이 외부 명령문의 부분임을 의미한다.
- This is one way to see whether multiple conditions are satisfied.
  - 이는 여러 조건이 만족되는지 확인하는 한 방법이다.

<br>

- For example:

```python
num = 12

if num > 5:
  print("Bigger than 5")
  if num <= 47:
    print("Between 5 and 47")
    
# Bigger than 5
# Between 5 and 47
```

[코드 실행 확인](https://code.sololearn.com/299/#py)

<br>

<br>

#### QUIZ

- What part of an if statement should be indented?
  - if 문의 어떤 부분을 들여쓰기 해야 하는가?

> [] The first line
>
> [] All of it
>
> [x] `The statements within it`

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
spam = 7

if spam > 5:
  print("five")
  
if spam > 8:
  print("eight")
```

> `five`

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
num = 7

if num > 3:
  print("3")
  if num < 5:
    print("5")
    if num == 7:
      print("7")
```

> `3`

<br>

<br>