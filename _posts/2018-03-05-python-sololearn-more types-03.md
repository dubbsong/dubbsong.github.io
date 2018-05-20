---
layout: post
title: "SoloLearn 번역 - 03. Dictionaries2 (More Types)"
categories: dev
tags: python
---

## Dictionaries 04

- Just like lists, dictionary keys can be assigned to different values.
  - 배열과 마찬가지로, dictionary key를 다른 값으로 지정할 수 있다.
- However, unlike lists, a new dictionary key can also be assigned a value, not just ones that already exist.
  - 하지만, 배열과 달리, 새 dictionary key는 이미 존재하는 값뿐만 아니라 값을 할당할 수도 있다.

```python
squares = {1: 1, 2: 4, 3: "error", 4: 16,}
squares[8] = 64
squares[3] = 9
print(squares)
```

<br>

- Result:

```python
{8: 64, 1: 1, 2: 4, 3: 9, 4: 16}
```

------

<br>

## Dictionaries 05

- To determine whether a key is in a dictionary, you can use **in** and **not in**, just as you can for a list.
  - dictionary에 key가 있는지 확인하려면, 배열의 경우와 마찬가지로, **in**과 **not in**을 사용할 수 있다.

<br>

- Example:

```python
nums = {
   1: "one",
   2: "two",
   3: "three",
}

print(1 in nums)
print("three" in nums)
print(4 not in nums)
```

<br>

- Result:

```python
>>>
True
False
True
>>>
```

------

<br>

## Dictionaries 06

- A useful dictionary method is **get**.
  - 유용한 dictionary 메소드는 **get**이다.
- It does the same thing as indexing, but if the key is not found in the dictionary it returns another specified value instead('None', by default).
  - 인덱싱과 동일한 작업을 하지만, key가 dictionary에 없으면 다른 지정된 값을 반환한다(기본값으로 'None').

<br>

- Example:

```python
pairs = {1: "apple",
        "orange": [2, 3, 4],
        True: False,
        None: "True",
}

print(pairs.get("orange"))
print(pairs.get(7))
print(pairs.get(12345, "not in dictionary"))
```

<br>

- Result:

```python
>>>
[2, 3, 4]
None
not in dictionary
>>>
```

------

<br>

## QUIZ

- What is the result of this code?

```python
primes = {1: 2, 2: 3, 4: 7, 7: 17}
print(primes[primes[4]])


17
```

<br>

- Drag and drop from the options below to print "Yes", if the key 112 is present in the dictionary named "pairs".

```python
if 112 in pairs:
   print("Yes")
```

<br>

- What is the result of this code?

```python
fib = {1: 1, 2: 1, 3: 2, 4: 3}
print(fib.get(4, 0) + fib.get(7, 5))


8
```

<br>