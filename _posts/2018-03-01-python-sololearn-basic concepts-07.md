---
layout: post
title: "SoloLearn - 07. Simple Input & Output (basic concepts)"
categories: dev
tags: python
---

## Output

- Usually, programs take **input** and process it to produce **output**.
  - 일반적으로, 프로그램은 입력을 받아 출력을 생성한다.
- In Python, you can use the **print** function to produce output.
  - Python에서는, 출력을 생성하기 위해 **print** 함수를 사용할 수 있다.
- This displays a textual representation of something to the screen.
  - 이것은 무언가의 텍스트 표현이 화면에 표시된다.

```python
>>> print(1 + 1)
2

>>> print("Hello\nWorld!")
Hello
World!
```

<br>

> When a string is printed, the quotes around it are not displayed.
>
> 문자열이 출력되었을 때, 주위의 따옴표는 표시되지 않는다.

<br>

## Input

- To get input from the user in Python, you can use the intuitively named **input** function.
  - Python에서 유저의 입력을 얻으려면, 직감적으로 명명된 **input** 함수를 사용할 수 있다.
- The function prompts the user for input, and returns what they enter as a string (with the contents automatically escaped).
  - 함수는 유저에게 입력을 요구하고, 문자열로 입력한 내용을 반환한다 (내용은 자동으로 이스케이프된다).

```python
>>> input("Enter something please: ")
Enter something please: This is what\nthe user enters!
   
'This is what\\nthe user enters!'
```

<br>

> The **print** and **input** functions aren't very useful at the Python console, which automatically does input and output.
>
> **print**와 **input** 함수는 Python 콘솔에서 유용하지 않다. 자동으로 입력과 출력을 한다.

> However, they are very useful in actual programs.
>
> 하지만, 실제 프로그램에서는 매우 유용하다.

<br>

## QUIZ

- What is the output of this code?

```python
>>> print('print("print")')
print("print")
```

<br>

- Fill in the blank to prompt for user input.

```python
>>> input("Enter a number:")
```

<br>