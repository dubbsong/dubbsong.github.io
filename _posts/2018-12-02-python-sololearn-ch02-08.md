---
layout: post
title: "(Control Structures 08) 리스트 연산"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- The item at a certain index in a list can be reassigned.
  - 리스트의 특정 색인에 있는 item을 재할당할 수 있다.

```python
nums = [4, 4, 4, 4, 4]
nums[2] = 5
print(nums)

# [4, 4, 5, 4, 4]
```

[코드 실행 확인](https://code.sololearn.com/315/#py)

<br>

- Lists can be added and multiplied in the same way as strings.
  - 문자열과 같은 방식으로 리스트를 추가하고 곱할 수 있다.

```python
nums = [1, 2, 3]
print(nums + [4, 5, 6])
print(nums * 3)

# [1, 2, 3, 4, 5, 6]
# [1, 2, 3, 1, 2, 3, 1, 2, 3]
```

[코드 실행 확인](https://code.sololearn.com/316/#py)

<br>

> Lists and strings are similar in many ways \- strings can be thought of as lists of characters that can't be changed.
>
> 리스트는 문자열과 여러 면에서 비슷하다.
>
> 문자열을 변경할 수 없는 리스트로 생각할 수 있다.

<br>

- To check if an item is in a list, the `in` operator can be used.
  - 리스트에 item이 있는지 확인하기 위해, `in` 연산자를 사용할 수 있다.
- It returns `True` if the item occurs one or more times in the list, and `False` if it doesn't.
  - item이 리스트에서 한 번 이상 발생하면 `True`를 반환하고, 그렇지 않으면 `False`를 반환한다.

```python
words = ["spam", "egg", "spam", "sausage"]
print("spam" in words)
print("egg" in words)
print("tomato" in words)

# True
# True
# False
```

[코드 실행 확인](https://code.sololearn.com/317/#py)

<br>

> The `in` operator is also used to determine whether or not a string is a substring of another string.
>
> `in` 연산자는 문자열이 다른 문자열의 하위 문자열인지 확인하는 데에도 사용된다.

<br>

- To check if an item is not in a list, you can use the `not` operator in one of the following ways:
  - item이 리스트에 없는지 확인하기 위해, 다음 방법 중 한 가지 방법으로 `not` 연산자를 사용할 수 있다.

```python
nums = [1, 2, 3]
print(not 4 in nums)
print(4 not in nums)
print(not 3 in nums)
print(3 not in nums)

# True
# True
# False
# False
```

[코드 실행 확인](https://code.sololearn.com/318/#py)

<br>

<br>

#### QUIZ

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
nums = [1, 2, 3, 4, 5]
nums[3] = nums[1]
print(nums[3])
```

> `2`

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
nums = [10, 9, 8, 7, 6, 5]
nums[0] = nums[1] - 5

if 4 in nums:
  print(nums[3])
else:
  print(nums[4])
```

> `7`

<br>

<br>