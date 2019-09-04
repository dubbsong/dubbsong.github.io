---
layout: post
title: "(Control Structures 12) 간단한 계산"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

## Creating a Calculator

###### 계산기 생성하기

<br>

- This lesson is about an example Python project: a simple calculator.
  - 이 레슨은 간단한 계산기를 만드는 Python 프로젝트 예제이다.
- Each part explains a different section of the program.
  - 각 부분은 프로그램의 다른 섹션을 설명한다.
- The first section is the overall menu.
  - 첫 번째 섹션은 전체 메뉴이다.
- This keeps on accepting user input until the user enters "quit", so a `while` loop is used.
  - 전체 메뉴는 사용자가 "quit"을 입력할 때까지 사용자 입력을 계속 받아들이므로, `while` loop가 사용된다.

```python
while True:
  print("Options:")
  print("Enter 'add' to add two numbers")
  print("Enter 'subtract' to subtract two numbers")
  print("Enter 'multiply' to multiply two numbers")
  print("Enter 'divide' to divide two numbers")
  print("Enter 'quit' to end the program")
  user_input = input(": ")
  
  if user_input == "quit":
    break
  elif user_input == "add":
    ...
  elif user_input == "subtract":
    ...
  elif user_input == "multiply":
    ...
  elif user_input == "divide":
    ...
  else:
    print("Unknown input")
```

<br>

> The code above is the starting point for our program.
>
> 위의 코드는 우리 프로그램의 시작점이다.
>
> It accepts user input, and compares it to the options in the `if/elif` statements.
>
> 사용자 입력을 받아, `if/elif` 문의 옵션과 비교한다.
>
> The `break` statement is used to stop the while loop, in case the user inputs "quit".
>
> `break` 문은 사용자가 "quit"을 입력한 경우, while loop를 멈추는 데 사용된다.

<br>

- The next part of the program is getting the numbers the user wants to do something with.
  - 프로그램의 다음 부분은, 사용자가 원하는 숫자를 얻는 것이다.
- The code below shows this for the addition section of the calculator.
  - 아래 코드는 계산기의 추가 섹션에 대한 것을 보여준다.
- Similar code would have to be written for the other sections.
  - 다른 섹션에도 비슷한 코드를 작성해야 한다.

```python
elif user_input == "add":
  num1 = float(input("Enter a number: "))
  num2 = float(input("Enter another number: "))
```

<br>

- Now, when the user inputs "add", the program prompts to enter two numbers, and stores them in the corresponding variables.
  - 이제 사용자가 "add"를 입력하면, 프로그램은 두 개의 숫자를 입력하라는 prompt를 표시하고, 그 숫자들을 해당 변수에 저장한다.

<br>

> As it is, this code crashes if the user enters a non-numeric input when prompted to enter a number.
>
> 숫자를 입력하라는 prompt가 표시될 때, 사용자가 숫자가 아닌 입력을 하면 코드가 충돌한다.
>
> We will look at fixing problems like this in a later module.
>
> 다음 모듈에서 이와 같은 문제를 해결해보자.

<br>

- The final part of the program processes user input and display it.
  - 프로그램의 마지막 부분은, 사용자 입력을 처리하고 표시한다.

```python
elif user_input == "add":
  num1 = float(input("Enter a number: "))
  num2 = float(input("Enter another number: "))
  result = str(num1 + num2)
  print("The answer is " + result)
```

<br>

- We now have a working program that prompts for user input, and then calculates and prints the sum of the input.
  - 이제 사용자 입력을 요구하고, 입력의 합을 계산하고 출력하는 프로그램이 작동한다.

<br>

> Similar code would have to be written for the other branches (for subtraction, multiplication and division).
>
> 빼기, 곱하기, 나누기에 대해서도 비슷한 코드를 작성해야 한다.
>
> The output line could be put outside the `if` statements to omit repetition of code.
>
> 출력 줄을 `if` 문 바깥에 두어 코드 반복을 생략할 수 있다.

<br>

<br>

#### QUIZ

- If we were to replace the break statement in the code with a 'continue', what would happen?
  - 코드의 break 문을 'continue'로 변경하면 어떻게 되는가?

> It would run forever
>
> 계속 실행될 것이다.

<br>

- Why are the calls to float necessary in the code?
  - 코드에서 float 호출이 왜 필요한가?

> To convert user input to a float
>
> 사용자 입력을 부동 소수점 수(float)으로 변환하기 위해

<br>

- Fill in the blanks to make the calculator work for multiplication.
  - 곱셈에 대한 계산을 작성해라.

```python
elif user_input == "multiply":
  num1 = float(input("Enter a number: "))
  num2 = float(input("Enter another number: "))
  result = str(num1 * num2)
  print("The answer is " + result)
```

<br>

<br>