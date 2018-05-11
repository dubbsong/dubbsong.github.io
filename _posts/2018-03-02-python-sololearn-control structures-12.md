---
layout: post
title: "SoloLearn 번역 - 12. A Simple Calculator (Control Structures)"
categories: dev
tags: python
---

## Creating a Calculator (계산기 만들기)

- This lesson is about an example Python project: a simple calculator.
  - 이 강의는 Python 프로젝트 예제이다: 간단한 계산기.
- Each part explains a different section of the program.
  - 각 부분은 프로그램의 다른 섹션을 설명한다.
- The first section is the overall menu.
  - 첫 번째 섹션은 전체 메뉴이다.
- This keeps on accepting user input until the user enters "quit", so a **while** loop is used.
  - 유저가 "quit"을 입력할 때까지 유저 입력을 받아들이므로, **while** 루프가 사용된다.

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

> It accepts user input, and compares it to the options in the **if/elif** statements.
>
> 유저 입력을 받아들이고, **if/elif** 명령문의 옵션과 비교한다.

> The break statement is used to stop the while loop, in case the user inputs "quit".
>
> break 문은 유저가 "quit"을 입력한 경우, while 루프를 멈추는 데 사용된다.

------

<br>

## Creating a Calculator 02

- The next part of the program is getting the numbers the user wants to do something with.
  - 프로그램의 다음 부분은 유저가 무언가를 하고 싶어 하는 숫자를 얻는 것이다.
- The code below shows this for the addition section of the calculator.
  - 아래의 코드는 계산기의 추가 섹션에 대한 내용을 보여준다.
- Similar code would have to be written for the other sections.
  - 다른 섹션에 대해서도 비슷한 코드를 작성해야 한다.

```python
elif user_input == "add":
   num1 = float(input("Enter a number: "))
   num2 = float(input("Enter another number: "))
```

<br>

- Now, when the user inputs "add", the program prompts to enter two numbers, and stores them in the corresponding variables.
  - 이제 유저가 "add"를 입력하면, 프로그램은 두 개의 숫자를 입력하라는 메시지를 표시하고, 해당 변수에 저장한다.

<br>

> As it is, this code crashes if the user enters a non-numeric input when prompted to enter a number.
>
> 숫자를 입력하라는 메시지가 표시될 때, 유저가 숫자가 아닌 것을 입력하면 코드가 깨진다.

> We will look at fixing problems like this in a later module.
>
> 다음 모듈에서 이와 같은 문제를 해결할 것이다.

------

<br>

## Creating a Calculator 03

- The final part of the program processes user input and displays it.
  - 프로그램의 마지막 부분은 유저 입력을 처리하고 보여주는 것이다.
- The code for the addtion part is shown here.
  - 추가 부분에 대한 코드가 여기에 표시된다.

```python
elif user_input == "add":
   num1 = float(input("Enter a number: "))
   num2 = float(input("Enter another number: "))
   result = str(num1 + num2)
   print("The answer is " + result)
```

<br>

- We now have a working program that prompts for user input, and then calculates and prints the sum of the input.
  - 우리는 이제 작동하는 프로그램을 가지고 있다. 유저 입력에 대한 메시지를 표시하고, 계산하고, 입력의 합을 출력하는 프로그램을.

<br>

> Similar code would have to be written for the other branches (for subtraction, multiplication and division).
>
> 다른 부분에도 비슷한 코드를 작성해야 한다 (뺄샘, 곱셈, 나눗셈에도).

> The output line could be put outside the if statements to omit repetition of code.
>
> 출력 라인은 코드의 반복을 생략하기 위해 if 문 외부에 놓일 수 있다.

------

<br>

## QUIZ

- If we were to replace the break statement in the code with a 'continue', what would happen?
  - **It would run forever**
  - You would have to enter "quit" twice to exit
  - It would run in the same way

<br>

- Why are the calls to float necessary in the code?
  - To remove spaces from user input
  - **To convert user input to a float**
  - To check if user input is a number

<br>

- Fill in the blanks to make the calculator work for nultiplication.

```python
elif user_input == "multiply":
   num1 = float(input("Enter a number: "))
   num2 = float(input("Enter another number: "))
   result = str(num1 * num2)
   print("The answer is" + result)
```

<br>