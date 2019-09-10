---
layout: post
title: "(More Types 03) 딕셔너리 함수"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- Just like lists, dictionary keys can be assigned to different values.
  - 리스트와 마찬가지로, 딕셔너리 key도 다른 값으로 할당할 수 있다.
- However, unlike lists, a new dictionary key can also be assigned a value, not just ones that already exist.
  - 하지만 리스트와 달리, 새로운 딕셔너리 key에 값(이미 존재하는 값이 아닌)을 할당할 수 있다.

```python
squares = {1: 1, 2: 4, 3: "error", 4: 16}

squares[8] = 64
squares[3] = 9

print(squares)
# {1: 1, 2: 4, 3: 9, 4: 16, 8: 64}
```

[코드 실행 확인](https://code.sololearn.com/362/#py)

<br>

- To determine whether a key is in a dictionary, you can use `in` and `not in`, just as you can for a list.
  - key가 딕셔너리에 있는지 확인하기 위해, 리스트와 마찬가지로 `in`과 `not in`을 사용할 수 있다.

```python
nums = {
  1: "one",
  2: "two",
  3: "three"
}

print(1 in nums)
# True

print("three" in nums)
# False

print(4 not in nums)
# True
```

[코드 실행 확인](https://code.sololearn.com/363/#py)

<br>

- A useful dictionary method is `get`.
  - 유용한 딕셔너리 메소드는 `get`이다.
- It does the same thing as indexing, but if the key is not found in the dictionary it returns another specified value instead ('None', by default).
  - 색인화와 동일한 작업을 수행하지만, 딕셔너리에 key가 없는 경우, 지정된 값(기본값: 'None')을 대신 반환한다.

```python
pairs = {1: "apple", "orange": [2, 3, 4], True: False, None: "True"}

print(pairs.get("orange"))
# [2, 3, 4]

print(pairs.get(7))
# None

print(pairs.get(12345, "not in dictionary"))
# not in dictionary
```



<br>

<br>

#### QUIZ

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
primes = {1: 2, 2: 3, 4: 7, 7: 17}
print(primes[primes[4]])
```

> `17`

<br>

- Drag and drop from the options below to print "Yes", if the key 112 is present in the dictionary named "pairs".
  - key 112가 "pairs"라는 딕셔너리에 있는 경우, "Yes"를 출력해라.

```python
if 112 in pairs:
  print("Yes")
```

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
fib = {1: 1, 2: 1, 3: 2, 4: 3}
print(fib.get(4, 0) + fib.get(7, 5))
```

> `8` (3 \+ 5)

<br>

<br>