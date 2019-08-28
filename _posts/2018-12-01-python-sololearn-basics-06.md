---
layout: post
title: "(Basics 06) 문자열"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- If you want to use text in Python, you have to use a `string`.
  - Python에서 텍스트를 사용하려면, `문자열(string)`을 사용해야 한다.
- A string is created by entering text between `two single or double quotation marks`.
  - 문자열은 `두 개의 작은따옴표나 큰따옴표` 사이에 텍스트를 입력해서 생성한다.

- When the Python console displays a string, it generally uses single quotes.
  - Python 콘솔은 문자열을 표시할 때, 일반적으로 작은따옴표를 사용한다.
- The delimiter used for a string doesn't affect how it behaves in any way.
  - 문자열에 사용된 구분자(delimiter)는 문자열의 작동 방식에 영향을 미치지 않는다.

```python
>>> "How are you?"
# 'How are you?'

>>> 'All good.'
# 'All good.'
```

<br>

- Some characters can't be directly included in a string.
  - 일부 문자는 문자열에 직접 포함시킬 수 없다.
- For instance, double quotes can't be directly included in a double quote string; this would cause it to end prematurely.
  - 예를 들어, 큰따옴표는 큰따옴표 문자열에 직접 포함될 수 없다.
  - 큰따옴표 문자열에 큰따옴표가 포함된다면, 조기 종료된다.

<br>

- Characters like these must be escaped by placing a `backslash` before them.
  - 이와 같은 글자는 `백슬래시` 앞에 놓음으로써 이스케이프 해야 한다.
- Other common characters that must be escaped are newlines and backslashes.
  - 이스케이프 되어야 하는 다른 문자는, 줄 바꿈 문자(newline)와 백슬래시(backslash)이다.
- Double quotes only need to be escaped in double quote strings, and the same is true for single quote strings.
  - 큰따옴표는 큰따옴표 문자열에서만 이스케이프 해야 하고, 작은따옴표의 경우도 마찬가지이다.

```python
>>> 'Brian\'s mother: He\'s not the Messiah. He\'s a very naughty boy!'
# 'Brian's mother: He's not the Messiah. He's a very naughty boy!'
```

<br>

- `\n` represents a new line.
  - `\n`은 줄 바꿈 문자를 나타낸다.

<br>

> `Backslashes` can also be used to escape tabs, arbitrary Unicode characters, and various other things that can't be reliably printed.
>
> `백슬래시`는 탭, 임의의 유니코드 문자, 다양한 기타 조건을 이스케이프 하는 데 사용될 수도 있다.
>
> These characters are known as escape characters.
>
> 이러한 글자를 이스케이프 문자라고 한다.

<br>

<br>

#### Newlines

###### 줄 바꿈 문자

- Python provides an easy way to avoid manually writing "\\n" to escape newlines in a string.
  - Python은 문자열에서 줄 바꿈 문자를 이스케이프 하기 쉬운 방법을 제공한다.
- Create a string with `three sets of quotes`, and newlines that are created by pressing Enter are automatically escaped for you.
  - `세 개의 따옴표 세트`로 문자열을 생성하면, Enter를 눌러 생성된 줄 바꿈 문자가 자동으로 이스케이프 된다.

```python
>>> """Customer: Good morning.
Owner: Good morning, Sir. Welcome to the National Cheese Emporium."""

# 'Customer: Good morning.\nOwner: Good morning, Sir. Welcome to the National Cheese Emporium.'
```

<br>

<br>

#### QUIZ

- Complete the code to create a string containing "Hello World".
  - "Hello World"를 포함하는 문자열을 생성해라.

```python
>>> "Hello World"
# 'Hello World'
```

<br>

- Complete the code to create a string containing a double quote.
  - 큰따옴표가 포함된 문자열을 생성해라.

```python
>>> "\""
```

<br>

<br>