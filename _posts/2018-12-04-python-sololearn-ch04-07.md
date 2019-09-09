---
layout: post
title: "(Exception & Files 07) 파일 읽기"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- The contents of a file that has been opened in text mode can be read using the `read` method.
  - text mode에서 열린 파일의 내용은 `read` 메소드를 사용해서 읽을 수 있다.

```python
file = open("filename.txt", "r")
cont = file.read()
print(cont)
file.close()
```

<br>

> This will print all of the contents of the file "filename.txt".
>
> "filename.txt" 파일의 모든 내용이 출력된다.

<br>

- To read only a certain amount of a file, you can provide a number as an argument to the `read` function.
  - 특정 양의 파일만 읽기 위해, `read` 함수에 대한 인수로 숫자를 제공할 수 있다.
- This determines the number of `bytes` that should be read.
  - 이는 읽어야 할 `바이트(byte)` 수를 결정한다.
- You can make more calls to read on the same file object to read more of the file byte by byte.
  - 더 많은 파일을 바이트 단위로 읽기 위해, 동일한 file 객체에서 더 많은 호출을 읽을 수 있다.
- With no argument, read returns the rest of the file.
  - 인수가 없으면, read는 파일의 나머지 부분을 반환한다.

```python
file = open("filename.txt", "r")
print(file.read(16))
print(file.read(4))
print(file.read(4))
print(file.read())
file.close()
```

<br>

> Just like passing no arguments, negative values will return the entire contents.
>
> 인수를 전달하지 않는 것처럼, 음수 값은 전체 내용을 반환한다.

<br>

- After all contents in a file have been read, any attempts to read further from that file will return an empty string, because you are trying to read from the end of the file.
  - 파일의 모든 내용을 읽은 후에는 파일의 끝에서 읽으려고 하므로, 해당 파일에서 계속 읽으려고 하면 빈 문자열이 반환된다.

```python
file = open("filename.txt", "r")
file.read()
print("Re-reading")
print(file.read())
print("Finished")
file.close()

# Re-reading

# Finished
```

<br>

- To retrieve each line in a file, you can use the `readlines` method to return a list in which each element is a line in the file.
  - 파일에서 각 줄을 검색하기 위해, `readlines` 메소드를 사용해서 각 엘리먼트가 파일의 행인 리스트를 반환할 수 있다.

```python
file = open("filename.txt", "r")
print(file.readlines())
file.close()

# ['Line 1 text\n', 'Line 2 text\n', 'Line 3 text']
```

<br>

- You can also use a `for` loop to iterate through the lines in the file:
  - `for` loop를 사용해서 파일의 줄을 반복할 수도 있다.

```python
file = open("filename.txt". "r")

for line in file:
  print(line)
  
file.close()

# Line 1 text

# Line 2 text

# Line 3 text
```

<br>

> In the output, the lines are separated by blank lines, as the `print` function automatically adds a new line at the end of its output.
>
> 출력에서 줄은 공백 줄로 구분된다.
>
> `print` 함수는 출력의 끝에 자동으로 새로운 줄을 추가한다.

<br>

<br>

#### QUIZ

- Rearrange the code to open a file, read its contents, print them, and then close the file.
  - 파일을 열고, 읽고, 출력한 다음, 닫아라.

```python
file = open("test.txt")
cont = file.read()
print(cont)
file.close()
```

<br>

- How many characters would be in each line printed by this code, if one character is one byte?
  - 하나의 글자가 1바이트인 경우, 이 코드로 출력된 각 줄에는 몇 개의 글자가 있는가?

```python
file = open("filename.txt", "r")

for i in range(21):
  print(file.read(4))

file.close()
```

> `4`

<br>

- If the file test.txt has 7 lines of content, what will the following expression return?
  - text.txt 파일에 7줄의 내용이 있는 경우, 다음 표현식을 무엇을 반환하는가?

```python
len(open("test.txt").readlines())
```

> `7`

<br>

<br>