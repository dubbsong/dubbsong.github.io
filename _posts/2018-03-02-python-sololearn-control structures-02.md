---
layout: post
title: "SoloLearn - 02. if Statements (Control Structures)"
categories: dev
tags: python
---

## if Statements (if 문)

- You can use if statements to run code if a certain condition holds.
  - 특정 조건이 충족되면 if 문을 사용해서 코드를 실행할 수 있다.
- If an expression evaluates to **True**, some statements are carried out.
  - 표현식이 참으로 평가되면, 일부 작업 명령문이 수행된다.
- Otherwise, they aren't carried out.
  - 그렇지 않으면, 수행되지 않는다.
- An if statement looks like this:
  - if 문은 다음과 같다.

```python
if expression:
   statements
```

<br>

> Python uses **indentation** (white space at the beginning of a line) to delimit blocks of code.
>
> Python은 **들여쓰기**(라인의 시작 부분의 공백)를 사용해서 코드 블록을 구분한다.

> Other languages, such as C, use curly braces to accomplish this, but in Python indentation is mandatory;
>
> C와 같은 다른 언어는 중괄호를 사용해서 이를 수행하지만, Python에서 들여쓰기는 필수이다.

> programs won't work without it.
>
> 프로그램 없이는 작동하지 않는다.

> As you can see, the statements in the **if** should be indented.
>
> 보다시피, if 문은 들여쓰기 되어야 한다.

------

<br>

## if Statements 02

- Here is an example if statement:
  - 다음은 if 문 예제이다.

```python
if 10 > 5:
   print("10 greater than 5")
   
print("Program ended")
```

<br>

- The expression determines whether 10 is greater than five.
  - 표현식은 10이 5보다 큰지를 결정한다.
- Since it is, the indented statement runs, and "10 greater than 5" is output.
  - 10은 5보다 크므로, 들여쓰기 문이 실행되고, "10보다 큰 5"가 출력된다.
- Then, the unidented statement, which is not part of the if statement, is run, and "Program ended" is displayed.
  - 그런 다음, if 문제 포함되지 않은, 들여쓰기 되지 않은 작업 명령문이 실행되고, "Program ended"가 표시된다.

<br>

- Result:

```python
>>>
10 greater than 5
Program ended
>>>
```

<br>

- Notice the **colon** at the end of the expression in the if statement.
  - if 문에서 표현식 끝에 있는 **콜론**에 주목해라.

> As the program contains multiple lines of code, you should create it as a separate file and run it.
>
> 프로그램에 여러 줄의 코드가 포함되어 있으므로, 별도의 파일로 만들어서 실행해야 한다.

------

<br>

## if Statements 03

- To perform more complex checks, if statements can be nested, one inside the other.
  - 보다 복잡한 검사를 수행하려면, if 문을 중첩할 수 있다.
- This means that the inner if statement is the statement part of the outer one.
  - 즉, 내부 if 문은 외부 if 문의 일부이다.
- This is one way to see whether multiple conditions are satisfied.
  - 이는 여러 조건이 충족되는지 여부를 확인하는 한 가지 방법이다.

<br>

- For example:

```python
num = 12
if num > 5:
   print("Bigger than 5")
   if num <= 47:
      print("Between 5 and 47")
```

<br>

- Result:

```python
>>>
Bigger than 5
Between 5 and 47
>>>
```

------

<br>

## QUIZ

- What part of an if statement should be indented?
  - **The statements within it** (안에 있는 작업 명령)
  - All of it (모두)
  - The first line

<br>

- What is the output of this code?

```python
spam = 7
if spam > 5:
   print("five")
if spam > 8:
   print("eight")

five
```

<br>

- What is the output of this code?

```python
num = 7
if num > 3:
   print("3")
   if num < 5:
      print("5")
      if num == 7:
         print("7")
         
3
```

<br>