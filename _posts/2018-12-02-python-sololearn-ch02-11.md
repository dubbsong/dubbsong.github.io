---
layout: post
title: "(Control Structures 11) for Loops"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

## Loops

- Sometimes, you need to perform code on each item in a list.
  - 가끔 리스트의 각 item에 대해 코드를 수행해야 한다.
- This is called iteration, and it can be accomplished with a `while` loop and a counter variable.
  - 이를 반복(iteration)이라고 한다.
  - `while` loop와 카운터 변수를 사용해서 수행할 수 있다.

```python
words = ["Hello", "World", "Spam", "Eggs"]
counter = 0
max_index = len(words) - 1

while counter <= max_index:
  word = words[counter]
  print(word + "!")
  counter = counter + 1
  
# Hello!
# World!
# Spam!
# Eggs!
```

[코드 실행 확인](https://code.sololearn.com/326/#py)

<br>

> The example above iterates through all items in the list, accesses them using their indices, and prints them with exclamation marks.
>
> 위의 예제는 리스트의 모든 item을 반복한다.
>
> 그리고 색인을 사용해서 액세스한 다음, 느낌표와 함께 출력한다.

<br>

## for Loop

- Iterating through a list using a `while` loop requires quite a lot of code, so Python provides the `for` loop as a shortcut that accomplishes the same thing.
  - `while` loop를 사용해서 리스트를 반복하려면 많은 코드가 필요하다.
  - 그래서 Python은 `for` loop를 제공한다.
- The same code from the previous example can be written with a `for` loop, as follows:
  - 이전 예제와 동일한 코드를 다음과 같이 `for` loop로 작성할 수 있다.

```python
words = ["Hello", "World", "Spam", "Eggs"]

for word in words:
  print(word + "!")
```

[코드 실행 확인](https://code.sololearn.com/327/#py)

<br>

> The `for` loop in Python is like the `foreach` loop in other language.
>
> Python의 `for` loop는, 다른 언어의 ` foreach` loop와 동일하다.

<br>

- The `for` loop is commonly used to repeat some code a certain number of times.
  - 일반적으로 `for` loop는, 일부 코드를 특정 횟수만큼 반복하는 데 사용된다.
- This is done by combining for loops with `range` objects.
  - 아래 코드는 for loop를 `range` 객체와 결합해서 수행한다.

```python
for i in range(5):
  print("Hello")
  
# Hello
# Hello
# Hello
# Hello
# Hello
```

[코드 실행 확인](https://code.sololearn.com/328/#py)

<br>

<br>

#### QUIZ

- Which construct can be used to iterate through a list?
  - 리스트를 반복하는 데 사용할 수 있는 구문은 무엇인가?

> `Loops`

<br>

- Fill in the blanks to create a valid for loop.
  - 유효한 for loop를 생성해라.

```python
letters = ['a', 'b', 'c']

for i in letters:
  print(i)
```

<br>

- Fill in the blanks to create a for loop that prints only the even values in the range:
  - range에서 짝수 값만 출력하는 for loop를 생성해라.

```python
for i in range(0, 20, 2):
  print(i)
```

<br>

<br>