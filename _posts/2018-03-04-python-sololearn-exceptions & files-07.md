---
layout: post
title: "SoloLearn 번역 - 07. Reading Files (Exceptions & Files)"
categories: dev
tags: python
---

## Reading Files (파일 읽기)

- The contents of a file that has been opened in text mode can be read using the **read** method.
  - 텍스트 모드로 열린 파일의 내용은 **read** 메소드를 사용해서 읽을 수 있다.

```python
file = open("filename.txt", "r")
cont = file.read()
print(cont)
file.close()
```

<br>

> This will print all of the contents of the file "filename.txt".
>
> 이 작업은 "filename.txt" 파일의 모든 내용이 출력된다.

------

<br>

## Reading Files 02

- To read only a certain amount of a file, you can provide a number as an argument to the **read** function.
  - 특정 양의 파일만 읽으려면, **read** 함수에 인수로 숫자를 제공할 수 있다.
- This determines the number of **bytes** that should be read.
  - 읽어야 할 **bytes** 수를 결정한다.
- You can make more calls to **read** on the same file object to read more of the file byte by byte.
  - 동일한 파일 객체에서 더 많은 호출을 만들어 byte 단위로 더 많은 파일을 읽을 수 있다.
- With no argument, **read** returns the rest of the file.
  - 인수가 없다면, **read**는 파일의 나머지 부분을 반환한다.

```python
file = open("filename.txt", "r")
print(file.read(16))
print(file.read(4))
print(file.read(4))
print(file.read())
file.close()
```

------

<br>

## Reading Files 03

- After all contents in a file have been read, any attempts to read further from that file will return an empty string, because you are trying to read from the end of the file.
  - 파일의 모든 내용을 읽은 후, 해당 파일에서 더 읽으려고 하면, 파일의 끝에서 읽으려고 하기 때문에 빈 문자열이 반환된다.

```python
file = open("filename.txt", "r")
file.read()
print("Re-reading")
print(file.read())
print("Finished")
file.close()
```

<br>

- Result:

```python
>>>
Re-reading

Finished
>>>
```

------

<br>

## Reading Files 04

- To retrieve each line in a file, you can use the **readlines** method to return a list in which each element is a line in the file.
  - 파일의 각 라인을 검색하려면, **readlines** 메소드를 사용해서 각 요소가 파일의 라인인 배열을 반환할 수 있다.

<br>

- For example:

```python
file = open("filename.txt", "r")
print(file.readlines())
file.close()
```

<br>

- Result:

```python
>>>
['Line 1 text \n', 'Line 2 text \n', 'Line 3 text']
```

<br>

- You can also use a **for** loop to iterate through the lines in the file:

```python
file = open("filename.txt", "r")

for line in file:
   print(line)
   
file.close()
```

<br>

- Result:

```python
>>>
Line 1 text

Line 2 text

Line 3 text
>>>
```

<br>

> In the output, the lines are separated by blank lines, as the **print** function automatically adds a new line at the end of its output.
>
> 출력에서는, **print** 함수가 자동으로 출력의 끝에 새 라인을 추가하므로, 라인이 공백 라인으로 구분된다.

------

<br>

## QUIZ

- Rearrange the code to open a file, read its contents, print them, and then close the file.

```python
file = open("text.txt")
cont = file.read()
print(cont)
file.close()
```

<br>

- How many characters would be in each line printed by this code, if one character is one byte?
  - **4**

```python
file = open("filename.txt", "r")
for i in range(21):
   print(file.read(4))
file.close()
```

<br>

- Fill in the blanks to open a file, read its content and print its length.

```python
file = open("filename.txt", "r")
str = file.read()
print(len(str))
file.close()
```

<br>

- If the file text.txt has 7 lines of content, what will the following expression return?

```python
len(open("text.txt").readlines())

7
```

<br>