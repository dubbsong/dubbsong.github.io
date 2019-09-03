---
layout: post
title: "(Control Structures 07) 리스트"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- `Lists` are another type of object in Python.
  - Python에서 `리스트(list)`는 또 다른 타입의 객체이다.
- They are used to store an indexed list of items.
  - 색인된(indexed) 리스트의 item을 저장하는 데 사용된다.
- A list is created using `square brackets` with `commas` separating items.
  - `쉼표`로 구분된 item들을 `대괄호 []`로 감싸서 생성한다.
- The certain item in the list can be accessed by using its index in square brackets.
  - 리스트의 특정 item은, 대괄호 내 색인(index)을 사용해서 액세스할 수 있다.

```python
words = ["Hello", "World", "!"]
print(words[0])
print(words[1])
print(words[2])

# Hello
# World
# !
```

[코드 실행 확인](https://code.sololearn.com/311/#py)

<br>

> The first list item's index is `0`, rather than 1, as might be expected.
>
> 리스트 item의 첫 번째 색인은 1이 아닌 `0`이다.

<br>

- An empty list is created with an empty pair of square brackets.
  - 비어 있는 리스트는 빈 대괄호 쌍으로 생성한다.

```python
empty_list = []
print(empty_list)

# []
```

[코드 실행 확인](https://code.sololearn.com/312/#py)

<br>

> Most of the time, a comma won't follow the last item in a list.
>
> 대부분의 경우, 리스트의 마지막 item 뒤에는 쉼표를 사용하지 않는다.
>
> However, it is perfectly valid to place one there, and it is encouraged in some cases.
>
> 하지만 쉼표를 사용해도 완벽히 유효하다.
>
> 경우에 따라 권장된다.

<br>

- Typically, a list will contain items of a single item type, but it is also possible to include several different types.
  - 일반적으로, 리스트에 단일 item 타입의 item이 포함되지만, 여러 다른 타입도 포함될 수 있다.
- Lists can also be nested within other lists.
  - 리스트는 다른 리스트 내에 중첩될 수도 있다.

```python
number = 3
things = ["string", 0, [1, 2, number], 4.56]
print(things[1])
print(things[2])
print(things[2][2])

# 0
# [1, 2, 3]
# 3
```

[코드 실행 확인](https://code.sololearn.com/313/#py)

<br>

> Lists of lists are often used to represent 2D grids, as Python lacks the multidimensional arrays that would be used for this in other languages.
>
> Python에는 다차원 배열이 없으므로, 종종 2D 그리드(grid)를 나타내는 데 사용된다.

<br>

- Indexing out of the bounds of possible list values causes an IndexError.
  - 가능한 리스트 값의 범위를 벗어나면, IndexError가 발생한다.
- Some types, such as `strings`, can be indexed like lists.
  - `문자열`과 같은 일부 타입은, 리스트처럼 색인을 사용할 수 있다.
- Indexing `strings` behaves as though you are indexing a list containing each character in the string.
  - 인덱싱 `문자열`은, 문자열의 각 글자가 포함된 리스트를 인덱싱하는 것처럼 동작한다.
- For other types, such as integers, indexing them isn't possible, and it causes a TypeError.
  - 정수와 같은 다른 타입의 경우 인덱싱 할 수 없으며, TypeError가 발생한다.

```python
str = "Hello World"
print(str[6])

# W
```

[코드 실행 확인](https://code.sololearn.com/314/#py)

<br>

<br>

#### QUIZ

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
nums = [5, 4, 3, 2, 1]
print(nums[1])
```

> `4`

<br>

- How many items are in this list?
  - 이 리스트에는 몇 개의 item이 있는가?

```python
[2,]
```

> `1`

<br>

- Which line of code will cause an error?
  - 어떤 코드 줄이 에러를 발생하는가?

```python
num = [5, 4, 3, [2], 1]
print(num[0])
print(num[3][0])
print(num[5])
```

> `Line 4` (print(num\[5\]))

<br>

<br>