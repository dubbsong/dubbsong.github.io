---
layout: post
title: "(Functional Programming 07) set 함수"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- `Sets` are data structures, similar to lists or dictionaries.
  - `Set`은 리스트 또는 딕셔너리와 비슷한 데이터 구조이다.
- They are created using curly braces, or the `set` function.
  - 중괄호 또는 `set` 함수를 사용해서 생성된다.
- They share some functionality with lists, such as the use of `in` to check whether they contain a particular item.
  - 특정 item이 포함되어 있는지 확인하기 위해 `in`을 사용하는 등, 리스트와 일부 기능을 공유한다.

```python
num_set = {1, 2, 3, 4, 5}
word_set = set(["spam", "eggs", "sausage"])

print(3 in num_set)
print("spam" not in word_set)
```

[코드 실행 확인](https://code.sololearn.com/398/#py)

<br>

> To create an empty set, you must use `set()`, as `{}` creates an empty dictionary.
>
> `{}`가 빈 딕셔너리를 생성하므로, 빈 set을 생성하기 위해 `set()`을 사용해야 한다.

<br>

- Sets differ from lists in several ways, but share several list operations such as `len`.
  - set은 여러 면에서 리스트와 다르지만, `len`과 같은 여러 리스트 연산을 공유한다.
- They are unordered, which means that they can't be indexed.
  - 색인화할 수 없으므로, 불규칙적이다.
- They `cannot` contain duplicate elements.
  - 중복 엘리먼트를 포함할 수 없다.
- Due to the way they're stored, it's `faster` to check whether an item is part of a set, rather than part of a list.
  - 저장 방식으로 인해, item이 리스트의 일부가 아닌 set의 일부인지 확인하는 것이 `더 빠르다`.
- Instead of using `append` to add to a set, use `add`.
  - `append`를 사용해서 set에 추가하는 대신, `add`를 사용한다.
- The method `remove` removes a specific element from a set; `pop` removes an arbitrary element.
  - `remove` 메소드는 set의 특정 엘리먼트를 제거한다.
  - `pop` 메소드는 임의의 엘리먼트를 제거한다.

```python
nums = {1, 2, 1, 3, 1, 4, 5, 6}

print(nums)
# {1, 2, 3, 4, 5, 6}

nums.add(-7)
nums.remove(3)
# {1, 2, 4, 5, 6, -7}
```

[코드 실행 확인](https://code.sololearn.com/399/#py)

<br>

> Basic uses of `sets` include membership testing and the elimination of duplicate entries.
>
> `set`의 기본 사용에는, 멤버십 테스팅과 중복 항목 제거가 포함된다.

<br>

- Sets can be combined using mathematical operations.
  - 수학 연산을 사용해서  set을 결합할 수 있다.
- The `union` operator `|` combines two sets to form a new one containing items in either.
  - `union` 연산자 `|` 두 set을 결합해서, 둘 중 하나에 item을 포함하는 set을 형성한다.
- The `intersection` operator `&` gets items only in both.
  - `intersection` 연산자 `&`는 둘 모두에서 item을 가져온다.
- The `difference` operator \- gets items in the first set but not in the second.
  - `difference` 연산자 `-`는 첫 번째 set에서는 item을 가져오지만, 두 번째 set에서는 item을 가져오지 않는다.
- The `symmetric difference` operator `^` gets items in either set, but not both.
  - `symmetric difference` 연산자  `^`는 두 set 중 한 set에서 item을 가져온다.

```python
first = {1, 2, 3, 4, 5, 6}
second = {4, 5, 6, 7, 8, 9}

print(first | second)
# {1, 2, 3, 4, 5, 6, 7, 8, 9}

print(first & second)
# {4, 5, 6}

print(first - second)
# {1, 2, 3}

print(second - first)
# {8, 9, 7}

print(first ^ second)
# {1, 2, 3, 7, 8, 9}
```

[코드 실행 확인](https://code.sololearn.com/400/#py)

<br>

## Data Structures

###### 데이터 구조

- As we have seen in the previous lessons, Python supports the following data structures: `lists`, `dictionaries`, `tuples`, `sets`
  - 이전 레슨에서 살펴본 것처럼, Python은 다음과 같은 데이터 구조를 지원한다.
  - `리스트`, `딕셔너리`, `튜플`, `set`

<br>

#### When to use a dictionary:

###### 딕셔너리를 사용하는 경우:

- When you need a logical association between a `key:value` pair.
  - `key:value` 쌍 사이에 논리적 연관이 필요할 때
- When you need fast lookup for your data, based on a custom key.
  - 사용자 정의 key를 기반으로, 데이터를 빠르게 검색해야 할 때
- When your data is being constantly modified. Remember, dictionaries are mutable.
  - 데이터가 지속적으로 수정될 때
  - 딕셔너리는 mutable(변경 가능한)이다.

<br>

#### When to use the other types:

###### 다른 타입을 사용하는 경우:

- Use `lists` if you have a collection of data that does not need random access. Try to choose lists when you need a simple, iterable collection that is modified frequently.
  - 무작위 액세스가 필요하지 않은 데이터의 collection이 있는 경우,  `리스트`를 사용한다.
  - 자주 수정되는 단순하고 반복 가능한 collection이 필요할 때 리스트를 선택한다.
- Use a `set` if you need uniqueness for the elements.
  - 엘리먼트에 고유성이 필요한 경우, `set`을 사용한다.
- Use `tuples` when your data cannot change.
  - 데이터를 변경할 수 없는 경우, `튜플`을 사용한다.

<br>

> Many times, a `tuple` is used in combination with a `dictionary`, for example, a `tuple` might represent a key, because it's immutable.
>
> `튜플`은 `딕셔너리`와 함께 사용되는 경우가 많다.
>
> 예를 들어, `튜플`은 key가 immutable(변경 불가능한)이므로 key를 나타낼 수 있다.

<br>

<br>

#### QUIZ

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
letters = {"a", "b", "c", "d"}

if "e" not in letters:
  print(1)
else:
  print(2)
```

> `1`

<br>

- Fill in the blanks to create a set, add the letter "z" to it, and print its length.
  - set을 생성한다.
  - 문자 "z"를 추가하고, 길이를 출력한다.

```python
nums = {"a", "b", "c", "d"}
nums.add("z")

print(len(nums))
```

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```python
a = {1, 2, 3}
b = {0, 3, 4, 5}

print(a & b)
```

> `{3}`

<br>

- Which of the following data types does not allow duplicate values?
  - 어떤 데이터 타입이 중복 값을 허용하지 않는가?

> `Sets`

<br>

<br>