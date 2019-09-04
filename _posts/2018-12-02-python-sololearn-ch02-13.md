---
layout: post
title: "(Control Structures 13) QUIZ"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
list = [1, 1, 2, 3, 5, 8, 13]
print(list[list[4]])
```

> `8`

<br>

- What does this code do?
  - 이 코드는 무엇을 하는가?

```python
for i in range(10):
  if not i % 2 == 0:
    print(i + 1)
```

> Print all the even numbers between 2 and 10
>
> 2와 10 사이의 모든 짝수를 출력한다.

<br>

- How many lines will this code print?
  - 이 코드는 몇 개의 줄을 출력하는가?

```python
while False:
  print("Looping...")
```

> `0`

<br>

- Fill in the blanks to print the first element of the list, if it contains even number of elements.
  - element의 수가 짝수라면, 리스트의 첫 번째 element를 출력해라.

```python
list = [1, 2, 3, 4]

if len(list) % 2 == 0:
  print(list[0])
```

<br>

- What does this code output?
  - 이 코드는 무엇을 출력하는가?

```python
letters = ['x', 'y', 'z']
letters.insert(1, 'w')
print(letters[2])
```

> `y`

<br>

- Fill in the blanks to iterate over the list using a for loop and print its values.
  - for loop를 사용해서 리스트를 반복하고 값을 출력해라.

```python
list = [1, 2, 3]

for var in list:
  print(var)
```

<br>

<br>