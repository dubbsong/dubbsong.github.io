---
layout: post
title: "SoloLearn 번역 - 07. Sets (Functional Programming)"
categories: dev
tags: python
---

## Sets (집합)

- **Sets** are data structures, similar to lists or dictionaries.
  - **집합**은 배열 또는 dictionary와 유사한 데이터 구조이다.
- They are created using curly braces, or the **set** function.
  - 중괄호 또는 **set** 함수를 사용해서 생성된다.
- They share some functionality with lists, such as the use of **in** to check whether they contain a particular item.
  - 특정 항목이 들어있는지 확인하기 위해 **in**을 사용하는 것처럼, 배열과 일부 상관관계를 공유한다.

```python
num_set = {1, 2, 3, 4, 5}
word_set = set(["spam", "eggs", "sausage"])

print(3 in num_set)
print("spam" not in word_set)
```

<br>

- Result:

```python
>>>
True
False
>>>
```

<br>

> To create an empty set, you must use **set()**, as **{}** creates an empty dictionary.
>
> **{}**가 빈 dictionary를 만드는 것처럼, 빈 집합을 만들려면, **set()**을 사용해야 한다.

------

<br>

## Sets 02

- Sets differ from lists in several ways, but share several list operations such as **len**.
  - 집합은 여러 가지 방법으로 배열과 다르지만, **len**처럼 여러 배열 연산을 공유한다.
- They are unordered, which means that they can't be indexed.
  - 순서가 정해지지 않았으므로, 인덱스를 생성할 수 없다.
- They **cannot** contain duplicate elements.
  - 중복 요소를 포함할 수 없다.
- Due to the way they're stored, it's **faster** to check whether an item is part of a set, rather than part of a list.
  - 저장 방법에 따라, 항목이 배열의 일부가 아닌 집합의 일부인지 확인하는 것이 **더 빠르다**.
- Instead of using **append** to add to a set, use **add**.
  - **append**를 사용해서 집합을 추가하는 대신, **add**를 사용해라.
- The method **remove** removes a specific element from a set; **pop** removes an arbitrary element.
  - **remove** 메소드는 특정 요소를 집합에서 제거한다. **pop**은 임의의 요소를 제거한다.

```python
nums = {1, 2, 1, 3, 1, 4, 5, 6}
print(nums)
nums.add(-7)
nums.remove(3)
print(nums)
```

<br>

- Result:

```python
>>>
{1, 2, 3, 4, 5, 6}
{1, 2, 4, 5, 6, -7}
>>>
```

<br>

> Basic uses of **sets** include membership testing and the elimination of duplicate entries.
>
> **집합**의 기본 사용에는 멤버십 테스트 및 중복된 항목의 제거가 포함된다.

------

<br>

## Sets 03

- Sets can be combined using mathematical operations.
  - 집합은 수학 연산을 사용해서 결합할 수 있다.
- The **union** operator **|** combines two sets to form a new one containing items in either.
  - **union** 연산자 **|**는 두 집합을 결합해서 둘 중 하나의 항목을 포함하는 새 집합을 형성한다.
- The **intersection** operator **&** gets items only in both.
  - **Intersection** 연산자 **&**는 두 집합 모두에서 항목만 가져온다.
- The **difference** operator **-** gets items in the first set but not in the second.
  - **difference** 연산자 **-**는 첫 번째 집합에서 항목을 가져오지만, 두 번째 집합에서는 가져오지 않는다.
- The **symmentric difference** operator **^** gets items in either set, but not both.
  - **symmetric difference** 연산자 **^**는 두 집합 중 하나에서 항목을 가져오지만, 둘 모두에서는 가져오지 않는다.

```python
first = {1, 2, 3, 4, 5, 6}
second = {4, 5, 6, 7, 8, 9}

print(first | second)
print(first & second)
print(first - second)
print(second - first)
print(first ^ second)
```

<br>

- Result:

```python
>>>
{1, 2, 3, 4, 5, 6, 7, 8, 9}
{4, 5, 6}
{1, 2, 3}
{8, 9, 7}
{1, 2, 3, 7, 8, 9}
>>>
```

------

<br>

## Data Structures

- As we have seen in the previous lessons, Python supports the following data structures: **lists**, **dictionaries**, **tuples**, **sets**.
  - 이전 강의에서 보았듯이, Python은 다음 데이터 구조를 지원한다: **lists**, **dictionaries**, **tuples**, **sets**.

<br>

#### When to use a dictionary: (dictionary를 사용할 때)

- When you need a logical association between a **key:value** pair.
  - **key:value** 쌍 사이에 논리적 연관이 필요할 때.
- When you need fast lookup for your data, based on a custom key.
  - custom key를 기반으로 데이터를 빠르게 찾아볼 때.
- When your data is being constantly modified.
  - 데이터가 지속적으로 수정되는 경우에.
- Remember, dictionaries are mutable.
  - dictionary는 mutable이라는 것을 기억해라.

<br>

#### When to use the other types: (다른 타입을 사용하는 경우)

- Use **lists** if you have a collection of data that does not need random access.
  - 임의 액세스가 필요하지 않은 데이터 모음이 있는 경우 **배열**을 사용해라.
- Try to choose lists when you need a simple, iterable collection that is modified frequently.
  - 자주 수정되는 단순하고 반복 가능한 모음이 필요할 때는 배열을 선택해라.
- Use a **set** if you need uniqueness for the elements.
  - 요소의 고유성이 필요한 경우 **set **을 사용해라.
- Use **tuples** when your data cannot change.
  - 데이터를 변경할 수 없는 경우 **tuple**을 사용해라.

<br>

> Many times, a **tuple** is used in combination with a **dictionary**, for example, a **tuple** might represent a key, because it's immutable.
>
> 많은 경우, **tuple**은 **dictionary**와 함께 사용된다. 예를 들어, **tuple**은 immutable이기 때문에 key를 나타낼 수 있다.

> `immutable`: cannot be changed after it's created

------

<br>

## QUIZ

- What is the output of this code?
  - 2
  - **1**
  - 1 2

```python
letters = {"a", "b", "c", "d"}
if "e" not in letters:
   print(1)
else:
   print(2)
```

<br>

- Fill in the blanks to create a set, add the letter "z" to it, and print its length.

```python
nums = {"a", "b", "c", "d"}
nums.add("z")
print(len(nums))
```

<br>

- What is the output of this code?

```python
a = {1, 2, 3}
b = {0, 3, 4, 5}
print(a & b)


{3}
```

<br>

- Which of the following data types does not allow duplicate values?
  - Lists
  - Tuples
  - Dictionaries
  - **Sets**

<br>