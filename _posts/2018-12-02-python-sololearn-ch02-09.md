---
layout: post
title: "(Control Structures 09) 리스트 함수"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- Another way of altering lists is using the `append` method.
  - 리스트를 변경하는 또 다른 방법은 `append` 메소드를 사용하는 것이다.
- This adds an item to the end of an existing list.
  - 기존 리스트의 끝에 item이 추가된다.

```python
nums = [1, 2, 3]
nums.append(4)
print(nums)

# [1, 2, 3, 4]
```

[코드 실행 확인](https://code.sololearn.com/319/#py)

<br>

> The `dot` before append is there because it is a `method` of the list class.
>
> append 전의 `점`은 리스트 클래스의 `메소드`이므로 존재한다.

<br>

- To get the number of items in a list, you can use the `len` function.
  - 리스트에서 item의 개수를 얻기 위해, `len` 함수를 사용할 수 있다.

```python
nums = [1, 3, 5, 2, 4]
print(len(nums))

# 5
```

[코드 실행 확인](https://code.sololearn.com/320/#py)

<br>

> Unlike `append`, `len` is a normal function, rather than a method.
>
> `append`와 달리, `len`은 메소드가 아닌 일반 함수이다.
>
> This means it is written before the list it is being called on, without a dot.
>
> 즉, 리스트가 호출되기 전에 점 없이 작성된다.

<br>

- The `insert` method is similar to `append`, except that it allows you to insert a new item at any position in the list, as opposed to just at the end.
  - `insert` 메소드는 `append`와 비슷하다.
  - 단, 리스트의 임의 위치에 새로운 item을 삽입할 수 있다.

```python
words = ["Python", "fun"]
index = 1
words.insert(index, "is")
print(words)

# ["python", "is", "fun"]
```

[코드 실행 확인](https://code.sololearn.com/321/#py)

<br>

- The `index` method finds the first occurrence of a list item and returns its index.
  - `index` 메소드는 리스트 item의 첫 item을 찾아서 해당 색인(index)을 반환한다.
- If the item isn't in the list, it raises a ValueError.
  - 리스트에 찾는 item이 없다면, ValueError가 발생한다.

```python
letters = ['a', 'b', 'c', 'd', 'e', 'f']
print(letters.index('a'))
print(letters.index('d'))
print(letters.index('z'))

# 0
# 3
# ValueError: 'z' is not in list
```

[코드 실행 확인](https://code.sololearn.com/322/#py)

<br>

> There are a few more useful functions and methods for lists.
>
> 리스트에 유용한 함수와 메소드가 몇 가지 더 있다.

> `max(list)`: Returns the list item with the maximum value
>
> 최대 값을 가진 리스트 item을 반환한다.
>
> `min(list)`: Returns the list item with minimum value
>
> 최소 값을 가진 리스트 item을 반환한다.
>
> `list.count(obj)`: Returns a count of how many times an item occurs in a list
>
> item이 리스트에서 몇 번 이나 발생했는지를 반환한다.
>
> `list.remove(obj)`: Removes an object from a list
>
> 리스트에서 객체를 제거한다.
>
> `list.reverse()`: Reverses objects in a list
>
> 리스트에서 객체를 반전한다.

<br>

<br>

#### QUIZ

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
words = ["Hello"]
words.append("World")
print(words[1])
```

> `World`

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
letters = ["a", "b", "c"]
letters.append("d")
print(len(letters))
```

> `4`

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
nums = [9, 8, 7, 6, 5]
nums.append(4)
nums.insert(2, 11)
print(len(nums))
```

> `7`

<br>

- Drag and drop from the options below to add 'z' to the end of the list and print the list's length.
  - 리스트의 끝에 'z'를 추가하고, 리스트의 길이를 출력해라.

```python
list.append('z')
print(len(list))
```

<br>

<br>