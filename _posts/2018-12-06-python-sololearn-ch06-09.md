---
layout: post
title: "(Functional Programming 09) QUIZ"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
nums = {1, 2, 3, 4, 5, 6}
nums = {0, 1, 2, 3} & nums
nums = filter(lambda x: x > 1, nums)

print(len(list(nums)))
```

> `2`

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
def power(x, y):
  if y == 0:
    return 1
  else:
    return x * power(x, y - 1)
  
print(power(2, 3))
```

> `8`

<br>

- Fill in the blanks to calculate the expression x \* (x \+ 1) using an anonymous function and call it for the number 6.
  - 익명 함수를 사용해서 표현식 x \* (x \+ 1)을 계산하고, 숫자 6을 호출해라.

```python
a = (lambda x: x * (x + 1))(6)

print(a)
```

<br>

- Fill in the blanks to leave only even numbers in the list.
  - 리스트에 짝수만 남겨라.

```python
nums = [1, 2, 8, 3, 7]
res = list(filter(lambda x: x % 2 == 0, nums))

print(res)
```

<br>

- Drag and drop from the options below to print only the items in the set "a" that are not in the set "b".
  - "b" set에 없고, "a" set의 item만 출력해라.

```python
print(a - b)
```

<br>

<br>