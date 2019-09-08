---
layout: post
title: "(Exception & Files 06) 파일 열기"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- You can use Python to read and write the contents of `files`.
  - Python을 사용해서 `파일`의 내용을 읽고 작성할 수 있다.
- Text files are the easiest to manipulate.
  - 텍스트 파일이 가장 조작하기 쉽다.
- Before a file can be edited, it must be opened, using the `open` function.
  - 파일을 편집하기 전에, `open` 함수를 사용해서 파일을 열어야 한다.

```python
myfile = open("filename.txt")
```

<br>

> The argument of the `open` function is the `path` to the file.
>
> `open` 함수의 인수는 파일의 `경로`이다.
>
> If the file is in the current working directory of the program, you can specify only its name.
>
> 파일이 프로그램의 현재 작업 디렉토리에 있는 경우, 파일 이름만 지정할 수 있다.

<br>

- You can specify the `mode` used to open a file by applying a second argument to the `open` function.
  - `open` 함수에 두 번째 인수를 적용해서, 파일을 여는 데 사용되는 `mode`를 지정할 수 있다.
- Sending "r" means open in read mode, which is the default.
  - "r"을 보내는 것은 read mode에서 열리는 것을 의미한다.
  - 이것이 기본값이다.
- Sending "w" means write mode, for rewriting the contents of a file.
  - "w"를 보내는 것은 파일의 내용을 다시 작성하는 write mode를 의미한다.
- Sending "a" means append mode, for adding new content to the end of the file.
  - "a"를 보내는 것은 파일의 끝에 새로운 내용을 추가하는 append mode를 의미한다.
- Adding "b" to a mode opens it in `binary` mode, which is used for non-text files (such as image and sound files).
  - mode에 "b"를 추가하면 `binary (2진)` mode로 열린다.
  - 이 mode는 텍스트가 아닌 파일(예: 이미지 및 사운드 파일)에 사용된다.

```python
# write mode
open("filename.txt", "w")

# read mode
open("filename.txt", "r")
open("filename.txt")

# binary write mode
open("filename.txt", "wb")
```

<br>

> You can use the \+ sign with each of the modes above to give them extra access to files.
>
> 각 mode와 \+ 기호를 사용해서 파일에 추가로 액세스할 수 있다.

<br>

- Once a file has been opened and used, you should close it.
  - 파일을 열고 사용한 후에는 닫아야 한다.
- This is done with the `close` method of the file object.
  - 이는 file 객체의 `close` 메소드로 수행된다.

```python
file = open("filename.txt", "w")

# do stuff to the file

file.close()
```

<br>

<br>

#### QUIZ

- Which function is used to access files?
  - 파일에 액세스하는 데 사용되는 함수는 무엇인가?

> `open`

<br>

- Drag and drop from the options below to open a file called "test.bin" in binary read mode.
  - 2진 read mode에서 "test.bin"이라는 파일을 열어라.

```python
file = open("test.bin", "rb")
```

<br>

- How would you close a file stored in a variable "text_file"?
  - 변수 "text_file"에 저장된 파일을 어떻게 닫아야 하는가?

> `text_file.close()`

<br>

<br>