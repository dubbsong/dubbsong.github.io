---
layout: post
title: "(Exception & Files 09) 파일로 작업하기"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- It is good practice to avoid wasting resources by making sure that files are always closed after they have been used.
  - 파일을 사용한 후에는 항상 파일을 닫아 자원을 낭비하지 않는 것이 좋다.
- One way of doing this is to use `try` and `finally`.
  - 이를 수행하는 한 가지 방법은, `try`와 `finally`를 사용하는 것이다.

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
> 위 코드는 에러가 발생하더라도 파일이 항상 닫힌다.

<br>

- An alternative way of doing this is using `with` statements.
  - 이를 수행하는 다른 방법은, `with` 문을 사용하는 것이다.
- This creates a temporary variable (often called `f`), which is only accessible in the indented block of the `with` statement.
  - 이는 임시 변수를 생성한다.
  - `with` 문의 들여쓰기 블록에서만 액세스할 수 있다.

```python
with.open("filename.txt") as f:
  print(f.read())
```

<br>

> The file is automatically closed at the end of the `with` statement, even if exceptions occur within it.
>
> 예외가 발생하더라도, `with` 문의 끝에서 파일이 자동으로 닫힌다.

<br>

<br>

#### QUIZ

- Will the close() function get called in this code?
  - 이 코드에서 close() 함수가 호출되는가?

```python
try:
  f = open("filename.txt")
  print(f.read())
  print(1 / 0)
finally:
  f.close()
```

> `Yes`

<br>

- Fill in the blanks to create a valid with statement, reading the contents of the file.
  - 파일의 내용을 읽는 유효한 with 문을 생성해라.

```python
with open("test.txt") as f:
  print(f.read())
```

<br>

<br>