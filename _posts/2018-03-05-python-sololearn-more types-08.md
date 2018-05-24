---
layout: post
title: "SoloLearn 번역 - 08. Useful Functions (More Types)"
categories: dev
tags: python
---

## String Functions (문자열 함수)

- Python contains many useful built-in functions and methods to accomplish common tasks.
  - Python에는 일반적인 작업을 수행하는 데 유용한 많은 내장 함수와 메소드가 포함되어 있다.
- **join** - joins a list of strings with another string as a separator.
  - **join** - 문자열의 배열을 다른 문자열과 구분 기호로 결합한다.
- **replace** - replaces one substring in a string with another.
  - **replace** - 문자열의 한 부분 문자열을 다른 문자열로 대체한다.
- **startswith** and **endswith** - determine if there is a substring at the start and end of a string, respectively.
  - **startswith**와 **endswith** - 문자열의 시작과 끝에 각가 부분 문자열이 있는지 체크한다.
- To change the case of a string, you can use **lower** and **upper**.
  - 문자열의 대소문자를 변경하려면, **lower**와 **upper**를 사용할 수 있다.
- The method **split** is the opposite of **join**, turning a string with a certain separator into a list.
  - 메소드 **split**은 **join**의 반대이며, 특정 구분 기호를 가진 문자열을 배열로 변환한다.

<br>

- Some examples:

```python
print(",".join(["spam", "eggs", "ham"]))
# prints "spam, eggs, ham"

print("Hello ME".replace("ME", "world"))
# prints "Hello world"

print("This is a sentence.".startswith("This"))
# prints "True"

print("This is a sentence.".endswith("sentence."))
# prints "True"

print("This is a sentence.".upper())
# prints "THIS IS A SENTENCE."

print("AN ALL CAPS SENTENCE".lower())
# prints "an all caps sentence"

print("spam, eggs, ham".split(","))
# prints "['spam', 'eggs', 'ham']"
```

------

<br>

## Numeric Functions (숫자 함수)

- To find the maximum or minimum of some numbers or a list, you can use **max** or **min**.
  - 일부 숫자나 배열의 최대 또는 최소 값을 찾으려면, **max** 또는 **min**을 사용할 수 있다.
- To find the distance of a number from zero (its absolute value), use **abs**.
  - 0(절대값)에서 숫자의 거리를 찾으려면, **abs**를 사용해라.
- To round a number to a certain number of decimal places, use **round**.
  - 숫자를 특정 소수 자리로 반올림하려면, **round**를 사용해라.
- To find the total of a list, use **sum**.
  - 배열의 총합을 찾으려면, **sum**을 사용해라.

<br>

- Some examples:

```python
print(min(1, 2, 3, 4, 0, 2, 1))
print(max([1, 4, 9, 2, 5, 6, 8]))
print(abs(-99))
print(abs(42))
print(sum([1, 2, 3, 4, 5]))
```

<br>

- Result:

```python
>>>
0
9
99
42
15
>>>
```

------

<br>

## List Functions (배열 함수)

- Often used in conditional statements, **all** and **any** take a list as an argument, and return **True** if all or any(respectively) of their arguments evaluate to **True** (and **False** otherwise).
  - 조건문에서 자주 사용되는 **all**과 **any**는 인수로써의 배열을 취하고, all 또는 any(각각)가 **True**로 판단되면 **True**를 반환한다. 그렇지 않으면 **False**를 반환한다.
- The function **enumerate** can be used to iterate through the values and indices of a list simultaneously.
  - 함수 **enumerate**를 사용해서 배열의 값과 인덱스를 동시에 반복할 수 있다.

<br>

- Example:

```python
nums = [55, 44, 33, 22, 11]

if all([i > 5 for i in nums]):
   print("All larger than 5")
   
if any([i % 2 == 0 for i in nums]):
   print("At least one is even")
   
for v in enumerate(nums):
   print(v)
```

<br>

- Result:

```python
>>>
All larger than 5
At least one is even
(0, 55)
(1, 44)
(2, 33)
(3, 22)
(4, 11)
>>>
```

------

<br>

## QUIZ

- Fill in the blanks to turn the string uppercase.

```python
a = "Spam"
b = a.upper()
```

<br>

- What is the result of this code?

```python
a = min([sum([11, 22]), max(abs(-30), 2)])
print(a)


30
```

<br>

- What is the result of this code?

```python
nums = [-1, 2, -3, 4, -5]
if all([abs(i) < 3 for i in nums]):
   print(1)
else:
   print(2)
   
   
2
```

<br>