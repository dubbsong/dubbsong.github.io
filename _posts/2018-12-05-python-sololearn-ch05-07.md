---
layout: post
title: "(More Type 07) 문자열 형식"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- So far, to combine strings and non-strings, you've converted the non-strings to strings and added them.
  - 지금까지 문자열과 문자열이 아닌(non-string) 것을 결합하기 위해, 문자열이 아닌 것을 문자열로 변환해서 추가했다.
- String formatting provides a more powerful way to embed non-strings within strings.
  - 문자열 형식은, 문자열에 문자열이 아닌 것을 포함시키는 강력한 방법을 제공한다.
- String formatting uses a string\'s `format` method to substitute a number of arguments in the string.
  - 문자열 형식은 문자열의 `format` 메소드를 사용해서 문자열에 여러 인수를 대체한다.

```python
nums = [4, 5, 6]
msg = "Numbers: {0} {1} {2}".format(nums[0], nums[1], nums[2])

print(msg)
# Numbers: 4 5 6
```

[코드 실행 확인](https://code.sololearn.com/375/#py)

<br>

> Each argument of the format function is placed in the string at the corresponding position, which is determined using the curly braces \{\}.
>
> format 함수의 각 인수는 해당 위치의 문자열에 위치한다.
>
> 중괄호 \{\}를 사용해서 결정된다.

<br>

- String formatting can also be done with named arguments.
  - 문자열 형식은 명명된 인수로 수행될 수도 있다.

```python
a = "{x}, {y}".format(x=5, y=12)

print(a)
# 5, 12
```

[코드 실행 확인](https://code.sololearn.com/376/#py)

<br>

<br>

#### QUIZ

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
print("{0}{1}{0}".format("abra", "cad"))
```

> `abracadabra`

<br>

- What is the result of this code?
  - 이 코드의 결과는 무엇인가?

```python
str = "{c}, {b}, {a}".format(a=5, b=9, c=7)

print(str)
```

> `7, 9, 5`

<br>

<br>