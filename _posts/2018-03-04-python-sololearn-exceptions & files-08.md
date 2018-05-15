---
layout: post
title: "SoloLearn 번역 - 08. Writing Files (Exceptions & Files)"
categories: dev
tags: python
---

## Writing Files (파일 쓰기)

- To write to files you use the **write** method, which writes a string to the file.
  - 파일에 쓰려면, 문자열을 파일에 쓰는 **write** 메소드를 사용한다.

<br>

- For example:

```python
file = open("newfile.txt", "w")
file.write("This has been written to a file")
file.close()

file = open("newfile.txt", "r")
print(file.read())
file.close()
```

<br>

- Result:

```python
>>>
This has been written to a file
>>>
```

<br>

> The "w" mode will create a file, if it does not already exist.
>
> "w" 모드는 아직 존재하지 않는 파일을 생성한다.

------

<br>

## Writing Files 02

- When a file is opened in write mode, the file's existing content is deleted.
  - 파일을 쓰기 모드로 열면, 파일의 기존 내용이 삭제된다.

```python
file = open("newfile.txt", "r")
print("Reading initial contents")
print(file.read())
print("Finished")
file.close()

file = open("newfile.txt", "w")
file.write("Some new text")
file.close()

file = open("newfile.txt", "r")
print("Reading new contents")
print(file.read())
print("Finished")
file.close()
```

<br>

- Result:

```python
>>>
Reading initial contents
some initial text
Finished
Reading new contents
Some new text
Finished
>>>
```

<br>

> As you can see, the content of the file has been overwritten.
>
> 보다시피, 파일의 내용을 덮어쓴다.

------

<br>

## Writing Files 03

- The **write** method returns the number of **bytes** written to a file, if successful.
  - **write** 메소드는 성공 시에, 파일에 쓰여진 **bytes**의 수를 반환한다.

```python
msg = "Hello world!"
file = open("newfile.txt", "w")
amount_written = file.write(msg)
print(amount_written)
file.close()
```

<br>

- Result:

```python
>>>
12
>>>
```

------

<br>

## QUIZ

- Which line of code writes "Hello world!" to a file?
  - **file.write("Hello world!")**
  - write("Hello world!", file)
  - write(file, "Hello world!")

<br>

- What happens if you open a file in write mode and then immediately close it?
  - Nothing changes
  - **The file contents are deleted**
  - A blank line is written to the file

<br>

- If a file write operation is successful, which one of these statements will be true?
  - **file.write(msg) == len(msg)**
  - file.write(msg) == True
  - file.write(msg) == msg

<br>