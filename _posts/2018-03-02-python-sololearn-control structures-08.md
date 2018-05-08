---
layout: post
title: "SoloLearn - 08. List Operations (Control Structures)"
categories: dev
tags: python
---

## List Operations (배열 연산)

- The item at a certain index in a list can be reassigned.
  - 배열의 특정 인덱스에 있는 항목을 재할당 할 수 있다.
- For example:

```python
nums = [7, 7, 7, 7, 7]
nums[2] = 5
print(nums)
```

<br>

- Result:

```python
>>>
[7, 7, 5, 7, 7]
>>>
```

<br>

## List Operations 02

- Lists can be added and multiplied in the same way as strings.
  - 배열은 문자열과 동일한 방법으로 추가하거나 곱할 수 있다.
- For example:

```python
nums = [1, 2, 3]
print(nums + [4, 5, 6])
print(nums * 3)
```

<br>

- Result:

```python
>>>
[1, 2, 3, 4, 5, 6]
[1, 2, 3, 1, 2, 3, 1, 2, 3]
>>>
```

<br>

> Lists and strings are similar in many ways -
>
> 배열과 문자열은 여러 면에서 유사하다.

> strings can be thought of as lists of characters that can't be changed.
>
> 문자열은 변경할 수 없는 문자 배열로 생각할 수 있다.

<br>

## List Operations 03

- To check if an item is in a list, the **in** operator can be used.
  - 항목이 배열 안에 있는지 확인하려면, **in** 연산자를 사용할 수 있다.
- It returns **True** if the item occurs one or more times in the list, and **False** if it doesn't.
  - 배열에서 항목이 한 번이나 한 번 이상 발생하면 **True**를 반환하고, 그렇지 않으면 **False**를 반환한다.

```python
words = ["spam", "egg", "spam", "sausage"]
print("spam" in words)
print("egg" in words)
print("tomato" in words)
```

<br>

- Result:

```python
>>>
True
True
False
>>>
```

<br>

> The **in** operator is also used to determine whether or not a string is a substring of another string.
>
> **in** 연산자는 문자열이 다른 문자열의 하위 문자열인지 확인하는 데에도 사용된다.

<br>

## List Operations 04

- To check if an item is not in a list, you can use the **not** operator in one of the following ways:
  - 배열 안에 항목이 없는지 확인하려면, 다음 중 한 가지 방법으로 **not** 연산자를 사용할 수 있다.

```python
nums = [1, 2, 3]
print(not 4 in nums)
print(4 not in nums)
print(not 3 in nums)
print(3 not in nums)
```

<br>

- Result:

```python
>>>
True
True
False
False
>>>
```

<br>

## QUIZ

- What is the result of this code?

```python
nums = [1, 2, 3, 4, 5]
nums[3] = nums[1]
print(nums[3])

2
```

<br>

- Fill in the blanks to create a list, reassign its 2nd element and print the whole list.

```python
nums = [33, 42, 56]
nums[1] = 22
print(nums)
```

<br>

- What is the result of this code?

```python
nums = [10, 9, 8, 7, 6, 5]
nums[0] = nums[1] - 5
if 4 in nums:
   print(nums[3])
else:
   print(nums[4])
   
7
```

<br>

- Fill in the blanks to print "Yes" if the list contains 'z':

```python
letters = ['a', 'b', 'z']
if "z" in letters:
   print("Yes")
```

<br>