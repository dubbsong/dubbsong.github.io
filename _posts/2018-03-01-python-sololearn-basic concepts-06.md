---
layout: post
title: "SoloLearn - 06. Strings (basic concepts)"
categories: dev
tags: python
---

## Strings (문자열)

- If you want to use text in Python, you have to use a `string`.
  - Python에서 텍스트를 사용하려면, `문자열`을 사용해야 한다.
- A string is created by entering text between **two single or double quotation marks**.
  - 문자열은 **작은 따옴표**나 **큰 따옴표** 사이에 텍스트를 입력해서 만든다.

<br>

- When the Python console displays a string, it generally uses single quotes.
  - Python 콘솔에 문자열이 표시되면, 일반적으로 작은 따옴표가 사용된다.
- The delimiter used for a string doesn't affect how it behaves in any way.
  - 문자열에 사용되는 구분 기호는 어떤 식으로든 동작하는 방식에 영향을 주지 않는다.

```python
>>> "Python is fun!"
'Python is fun!'

>>> 'Always look on the bright side of life'
'Always look on the bright side of life'
```

<br>

## Strings 02

- Some characters can't be directly included in a string.
  - 일부 문자는 문자열에 직접 포함될 수 없다.
- For instance, double quotes can't be directly included in a double quote string;
  - 예를 들어, 큰 따옴표는 큰 따옴표 문자열에 직접 포함될 수 없다.
- this would cause it to end prematurely.
  - 이것은 조기에 끝나게 할 것이다.

<br>

- Characters like these must be escaped by placing a **backslash** before them.
  - 이러한 문자는 앞에 **백 슬래시(\\)**를 넣어서 이스케이프 처리해야 한다.
- Other common characters that must be escaped are newlines and backslashes.
  - 이스케이프 처리해야 하는 다른 공통 문자는 개행과 백 슬래시이다.
- Double quotes only need to be escaped in double quote strings, and the same is true for single quote strings.
  - 큰 따옴표는 큰 따옴표 문자열에서만 이스케이프 처리해야 하며, 작은 따옴표 문자열에서도 마찬가지다.

```python
>>> 'Brian\'s mother: He\'s not the Messiah. He\'s a very naughty boy!'
```

<br>

- `\n` represents a new line.
  - `\n`은 개행을 나타낸다.

<br>

> **Backslashes** can also be used to escape tabs, arbitrary Unicode characters, and various other things that can't be reliably printed.
>
> **백 슬래시**는 탭, 임의의 유니코드 문자, 출력할 수 없는 여러 가지 요소를 이스케이프 처리하는 데에도 사용할 수 있다.

> These characters are known as escape characters.
>
> 이러한 문자는 이스케이프 문자라고 한다.

<br>

## Newlines (개행)

- Python provides an easy way to avoid manually writing "\n" to escape newlines in a string.
  - Python은 "\n"을 작성해서 문자열의 개행 문자를 이스케이프하지 않도록 하는 쉬운 방법을 제공한다.
- Create a string with **three sets of quotes**, and newlines that are created by pressing Enter are automatically escaped for you.
  - 3세트의 따옴표가 있는 문자열을 만들면, Enter키를 눌러서 생성된 줄 바꿈 문자가 자동으로 이스케이프 처리된다.

```python
>>> """Customer: Good morning.
Owner: Good morning, Sir. Welcome to the National Cheese Emporium."""

'Customer: Good morning.\nOwner: Good morning, Sir. Welcome to the National Cheese Emporium.'
```

<br>

> As you can see, the **\n** was automatically put in the output, where we pressed Enter.
>
> 보다시피, **\n**이 자동으로 출력에 입력되고, Enter키를 누른다.

<br>

## QUIZ

- Complete the code to create a string containing "Hello world".

```python
>>> "Hello world"
'Hello world'
```

<br>

- Complete the code to create a string containing a double quote.

```python
>>> "\""
```

<br>

- Fill in the missing part of the output.

```python
>>> """Fisrt line
second line"""

'First line \n second line'
```

<br>