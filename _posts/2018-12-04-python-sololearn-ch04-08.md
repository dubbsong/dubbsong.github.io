---
layout: post
title: "(Exception & Files 08) 파일 쓰기"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- To write to files you use the `write` method, which writes a string to the file.
  - 파일에 문자열을 작성하기 위해, `write` 메소드를 사용한다.

```python
file = open("newfile.txt", "w")
file.write("This has been written to a file")
file.close()

file = open("newfile.txt", "r")
print(file.read())
file.close()

# This has been written to a file
```

[코드 실행 확인](https://code.sololearn.com/354/#py)

<br>

> The "w" mode will create a file, if it does not already exist.
>
> 파일이 없는 경우, "w" mode는 파일을 생성한다.

<br>

- When a file is opened in write mode, the file's existing content is deleted.
  - write mode에서 파일을 열 때, 파일의 기존 내용이 제거된다.

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

# Reading initial contents
# Some initial text
# Finished
# Reading new contents
# Some new text
# Finished
```

[코드 실행 확인](https://code.sololearn.com/355/#py)

<br>

> As you can see, the content of the file has been overwritten.
>
> 보다시피, 파일의 내용을 덮어썼다.

<br>

- The `write` method returns the number of `bytes` written to a file, if successful.
  - 성공한 경우, `write` 메소드는 파일에 작성된 `바이트` 수를 반환한다.

```python
msg = "Hello World"
file = open("newfile.txt", "w")
amount_written = file.write(msg)
print(amount_written)
file.close()

# 12
```

[코드 실행 확인](https://code.sololearn.com/356/#py)

<br>

> To write something other than a string, it needs to be converted to a string first.
>
> 문자열 이외의 것을 작성하기 위해, 먼저 문자열로 변환해야 한다.

<br>

<br>

#### QUIZ

- Which line of code writes "Hello World" to a file?
  - 어떤 코드 줄이 파일에 "Hello World"를 작성하는가?

```python
file.write("Hello World")
```

<br>

- What happens if you open a file in write mode and then immediately close it?
  - write mode에서 파일을 연 다음 즉시 닫으면 어떻게 되는가?

> The file contents are deleted
>
> 파일 내용이 제거된다.

<br>

- If a file write operation is successful, which one of these statements will be true?
  - 파일 작성 작업이 성공한 경우, 다음 명령문 중 참(true)인 것은 무엇인가?

> [] file.write(msg) == msg
>
> [] file.write(msg) == True
>
> [x] `file.write(msg) == len(msg)`	

<br>

<br>