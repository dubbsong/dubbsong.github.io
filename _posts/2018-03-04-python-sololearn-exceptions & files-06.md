---
layout: post
title: "SoloLearn 번역 - 06. Opening Files (Exceptions & Files)"
categories: dev
tags: python
---

## Opening Files (파일 열기)

- You can use Python to read and write the contents of **files**.
  - Python을 사용해서 파일의 내용을 읽고 쓸 수 있다.
- Text files are the easiest to manipulate.
  - 텍스트 파일을 조작하는 것이 가장 쉽다.
- Before a file can be edited, it must be opened, using the **open** function.
  - 파일을 편집하려면 먼저 **open** 함수를 사용해서 파일을 열어야 한다.

```python
myfile = open("filename.txt")
```

<br>

> The argument of the **open** function is the **path** to the file.
>
> **open** 함수의 인수는 파일 **경로**이다.

> If the file is in the current working directory of the program, you can specify only its name.
>
> 만약 파일이 프로그램의 현재 작업 디렉토리에 있다면, 이름만 지정할 수 있다.

------

<br>

## Opening Files 02

- You can specify the **mode** used to open a file by applying a second argument to the **open** function.
  - **open** 함수에 두 번째 인수를 적용해서 파일을 여는 데 사용되는 **mode**를 지정할 수 있다.
- Sending "r" means open in read mode, which is the default.
  - "r" 전송은 읽기 모드에서 여는 것을 의미하며, 기본값이다.
- Sending "w" means write mode, for rewriting the contents of a file.
  - "w" 전송은 쓰기 모드를 의미하며, 파일의 내용을 다시 쓰기 위한 것이다.
- Sending "a" means append mode, for adding new content to the end of the file.
  - "a" 전송은 추가 모드를 의미하며, 파일의 끝에 새로운 내용을 추가하기 위한 것이다.

<br>

- Adding "b" to a mode opens it in **binary** mode, which is used for non-text files (such as image and sound files).
  - "b"를 모드에 추가하면 **binary** 모드로 열리는데, 이 모드는 non-text 파일에 사용된다 (이미지나 사운드 파일에).

<br>

- For example:

```python
# write mode
open("filename.txt", "w")

# read mode
open("filename.txt", "r")
open("filename.txt")

# binary write mode
open("filename.txt", "wb")
```

------

<br>

## Opening Files 03

- Once a file has been opened and used, you should close it.
  - 파일을 열고 사용한 후에는 닫아야 한다.
- This is done with the **close** method of the file object.
  - 이 작업은 파일 객체의 **close** 메소드를 사용해서 수행된다.
  - `method`: like a function, but it runs

```python
file = open("filename.txt", "w")
# do stuff to the file
file.close()
```

<br>

> We will read/write content to files in the upcoming lessons.
>
> 다가올 강의에서 파일의 내용을 읽고 쓰게 될 것이다.

------

<br>

## QUIZ

- Which function is used to access files?
  - **open**

<br>

- Drag and drop from the options below to open a file called "test.bin" in binary read mode.

```python
file = open("text.bin", "rb")
```

<br>

- How would you close a file stored in a variable "text_file"?
  - **text_file.close()**
  - close(text_file)
  - close("text_file")

<br>