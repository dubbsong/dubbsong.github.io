---
layout: post
title: "SoloLearn 번역 - 09. List Functions (Control Structures)"
categories: dev
tags: python
---

## List Functions (배열 함수)

- Another way of altering lists is using the **append** method.
  - 배열을 변경하는 또 다른 방법은 **append** 메소드를 사용하는 것이다.
  - `method`: like a function, but it runs
- This adds an item to the end of an existing list.
  - 이렇게 하면 기존 배열의 끝에 항목이 추가된다.

```python
nums = [1, 2, 3]
nums.append(4)
print(nums)
```

<br>

- Result:

```python
>>>
[1, 2, 3, 4]
>>>
```

<br>

> The **dot** before append is there because it is a method of the list class.
>
> append 전의 **점(.)**은 배열 클래스의 메소드이기 때문에 거기에 있는 것이다.

> Methods will be explained in a later lesson.
>
> 메소드는 이후 강의에서 설명할 것이다.

------

<br>

## List Functions 02

- To get the number of items in a list, you can use the **len** function.
  - 배열에서 항목의 수를 얻기 위해서는, **len** 함수를 사용할 수 있다.
  - `function`: a parameterized sequence of statements

```python
nums = [1, 3, 5, 2, 4]
print(len(nums))
```

<br>

- Result:

```python
>>>
5
>>>
```

<br>

> Unlike **append**, **len** is a normal function, rather than a method.
>
> **append**와 달리, **len**은 메소드가 아닌 일반 함수이다.

> This means it is written before the list it is being called on, without a dot.
>
> 즉, 점(.) 없이, 배열이 호출되기 전에 작성된다.

------

<br>

## List Functions 03

- The **insert** method is similar to **append**, except that it allows you to insert a new item at any position in the list, as opposed to just at the end.
  - **insert** 메소드는 **append** 메소드와 유사하지만, 배열의 어느 자리에나 삽입이 가능하다.

```python
words = ["Python", "fun"]
index = 1
words.insert(index, "is")
print(words)
```

<br>

- Result:

```python
>>>
['Python', 'is', 'fun']
>>>
```

------

<br>

## List Functions 04

- The **index** method finds the first occurrence of a list item and returns its index.
  - **index** 메소드는 배열 항목의 첫 번째 상황을 찾고, 해당 인덱스를 반환한다.
- If the item isn't in the list, it raises a ValueError.
  - 만약 배열에 항목이 없으면, ValueError가 발생한다.

```python
letters = ['p', 'q', 'r', 's', 'p', 'u']
print(letters.index('r'))
print(letters.index('p'))
print(letters.index('z'))
```

<br>

- Result:

```python
>>>
2
0
ValueError: 'z' is not in list
>>>
```

<br>

> There are a few more useful functions and methods for lists.
>
> 배열에는 몇 가지 유용한 함수와 메소드가 있다.

> `max(list)`: Returns the list item with the maximum value
>
> `min(list)`: Returns the list item with the minimum value
>
> `list.count(obj)`: Returns a count of how many times an item occurs in a list
>
> `list.remove(obj)`: Removes an object from a list
>
> `list.reverse()`: Reverses objects in a list

------

<br>

## QUIZ

- What is the result of this code?

```python
words = ["hello"]
words.append("world")
print(words[1])

world
```

<br>

- What is the result of this code?

```python
letters = ["a", "b", "c"]
letters.append("d")
print(len(letters))

4
```

<br>

- What is the result of this code?

```python
nums = [9, 8, 7, 6, 5]
nums.append(4)
nums.insert(2, 11)
print(len(nums))

7
```

<br>

- Drag and drop from the options below to add 'z' to the end of the list and print the list's length.

```python
list.append('z')
print(len(list))
```

<br>