---
layout: post
title: "SoloLearn - 03. else Statements (Control Structures)"
categories: dev
tags: python
---

## else Statements (else 문)

- An **else** statement follows an if statement, and contains code that is called when the if statement evaluates to **False**.
  - **else** 문은 if 문 다음에 나오며, if 문이 **False**로 평가될 때 호출되는 코드를 포함한다.
- As with if statements, the code inside the block should be indented.
  - if 문과 마찬가지로, 블록 내부의 코드는 들여쓰기 되어야 한다.

```python
x = 4
if x == 5:
   print("Yes")
else:
   print("No")
```

<br>

- Result:

```python
>>>
No
>>>
```

------

<br>

## else Statements 02

- You can chain **if** and **else** statements to determine which option in a series of possibilities is true.
  - **if** 문과 **else** 문을 연결해서 일련의 가능성 중에서 어떤 옵션이 사실인지 확인할 수 있다.
- For example:

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
```

<br>

- Result:

```python
>>>
Number is 7
>>>
```

------

<br>

## elif Statements 03

- The `elif` (short for else if) statement is a shortcut to use when chaining if and else statements.
  - `elif` (else if 의 축약) 문은 if 문과 else 문을 연결할 때 사용하기 위한 축약형이다.
- A series of if elif statements can have a final else block, which is called if none of the if or elif expressions is True.
  - 일련의 if elif 문은 마지막에 else 블록을 가질 수 있다. if 또는 elif 표현식 중 아무것도 True가 아닌 경우 호출된다.
- For example:

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
```

<br>

- Result:

```python
>>>
Number is 7
>>>
```

<br>

> In other programming languages, equivalents to the **elif** statement have varying names, including **else if**, **elseif** or **elsif**.
>
> 다른 프로그래밍 언어에서는, **else if**, **elseif** 또는 **elsif**를 포함해서, **elif** 문에 해당하는 이름이 다양하다.

------

<br>

## QUIZ

- What is the result of this code?

```python
if 1 + 1 == 2:
   if 2 * 2 == 8:
      print("if")
	else:
      print("else")
      
else
```

<br>

- Fill in the blanks to compare the variables and output the corresponding text:

```python
x = 10
y = 20
if x > y:
   print("if statement")
else:
   print("else statement")
```

<br>

- A shorter option for an "else if" statement is:
  - **elif**

<br>