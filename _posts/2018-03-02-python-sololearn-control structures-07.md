---
layout: post
title: "SoloLearn - 07. Lists (Control Structures)"
categories: dev
tags: python
---

## Lists (배열)

- **Lists** are another type of object in Python.
  - **배열**은 Python에서 또 다른 타입의 객체이다.
- They are used to store an indexed list of items.
  - 배열은 항목의 인덱스 목록을 저장하는 데 사용된다.
- A list is created using **square brackets** with **commas** separating items.
  - 배열은 항목을 구분하는 **쉼표**와 **대괄호**를 사용해서 만들어진다.
- The certain item in the list can be accessed by using its index in square brackets.
  - 배열의 특정 항목은 대괄호 안에 인덱스를 사용해서 엑세스 할 수 있다.
- For example:

```python
words = ["Hello", "world", "!"]
print(words[0])
print(words[1])
print(words[2])
```

<br>

- Result:

```python
>>>
Hello
world
!
>>>
```

<br>

> The first list item's index is **0**, rather than 1, as might be expected.
>
> 배열의 첫 번째 인덱스는 1이 아니라, **0**이다.

<br>

## Lists 02

- An empty list is created with an empty pair of square brackets.
  - 빈 대괄호 쌍으로 빈 배열이 만들어진다.

```python
empty_list = []
print(empty_list)
```

<br>

- Result:

```python
>>>
[]
>>>
```

<br>

> Most of the time, a comma won't follow the last item in a list.
>
> 대부분의 경우, 쉼표는 배열의 마지막 항목을 따르지 않는다.

> However, it is perfectly valid to place one there, and it is encouraged in some cases.
>
> 하지만, 어떤 경우에는 마지막 항목에 배치하는 것이 완벽하게 유효하고, 권장되기도 한다.

<br>

## List 03

- Typically, a list will contain items of a single item type, but it is also possible to include several different types.
  - 일반적으로, 배열은 단일 항목 타입의 항목이 포함되지만, 여러 다른 타입을 포함할 수도 있다.
- Lists can also be nested within other lists.
  - 배열은 다른 배열에 중첩될 수도 있다.

```python
number = 3
things = ["string", 0, [1, 2, number], 4.56]
print(things[1])
print(things[2])
print(things[2][2])
```

<br>

- Result:

```python
>>>
0
[1, 2, 3]
3
>>>
```

<br>

> Lists of lists are often used to represent 2D grids, as Python lacks the multidimensional arrays that would be used for this in other languages.
>
> 배열 안의 배열은 2D 격자를 표현하기 위해 종종 사용된다.
>
> Python에는 다차원 배열이 없기 때문에, 다른 언어에서 사용되는 것처럼.

<br>

## Lists 04

- Indexing out of the bounds of possible list values causes an IndexError.
  - 가능한 범위 밖의 배열 값을 인덱싱하면 IndexError가 발생한다.
- Some types, such as **strings**, can be indexed like lists.
  - **문자열**과 같은 일부 타입은, 배열처럼 인덱싱 할 수 있다.
- Indexing **strings** behaves as though your are indexing a list containing each character in the string.
  - 문자열 인덱싱은 문자열 안에 각 문자를 포함하는 배열을 인덱싱하는 것처럼 동작한다.
- For other types, such as integers, indexing them isn't possible, and it causes a TypeError.
  - 정수와 같은 다른 타입의 경우, 인덱싱이 불가능하고 TypeError가 발생한다.

```python
str = "Hello world!"
print(str[6])
```

<br>

- Result:

```python
>>>
W
>>>
```

<br>

## QUIZ

- What is the result of this code?

```python
nums = [5, 4, 3, 2, 1]
print(num[1])

4
```

<br>

- How many items are in this list?

```python
[2,]

1
```

<br>

- Fill in the blanks to create a list and print its 3rd element.

```python
list = [42, 55, 67]
print(list[2])
```

<br>

- Which line of code will cause an error?
  - **line 4** (**print(num[5])**)

```python
num = [5, 4, 3, [2], 1]
print(num[0])
print(num[3][0])
print(num[5])
```

<br>