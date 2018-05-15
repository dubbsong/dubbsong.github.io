---
layout: post
title: "SoloLearn 번역 - 09. Working with Files (Exceptions & Files)"
categories: dev
tags: python
---

## Working with Files (파일 작업)

- It is good practice to avoid wasting resources by making sure that files are always closed after they have been used.
  - 파일을 사용한 후에는 항상 파일을 닫아서 리소스를 낭비하지 않는 것이 좋다.
- One way of doing this is to use **try** and **finally**.
  - 이렇게 하는 한 가지 방법은 **try**와 **finally**를 사용하는 것이다.

```python
try:
   f = open("filename.txt")
   print(f.read())
finally:
   f.close()
```

<br>

> This ensures that the file is always closed, even if an error occurs.
>
> 이렇게 하면 에러가 발생해도 파일이 항상 닫힌다.

------

<br>

## Working with Files 02

- An alternative way of doing this is using **with** statements.
  - 이 작업을 수행하는 또 다른 방법은 **with** 문을 사용하는 것이다.
- This creates a temporary variable (often. called f), which is only accessible in the indented block of the **with** statement.
  - 이렇게 하면 임시 변수가 작성되고, 이 변수는 **with** 문의 들여쓰기 된 블록에서만 엑세스 할 수 있다.

```python
with open("filename.txt") as f:
   print(f.read())
```

<br>

> The file is automatically closed at the end of the **with** statement, even if exceptions occur within it.
>
> 파일은 예외가 발생하더라도 **with** 문의 끝에서 자동으로 닫히게 된다.

------

<br>

## QUIZ

- Will the close() function get called in this code?
  - **Yes**
  - No

```python
try:
   f = open("filename.txt")
   print(f.read())
   print(1 / 0)
finally:
   f.close()
```

<br>

- Fill in the blanks to create a valid with statement, reading the contents of the file.

```python
with open("text.txt") as f:
   print(f.read())
```

<br>