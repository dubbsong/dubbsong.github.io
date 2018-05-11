---
layout: post
title: "SoloLearn 번역 - 11. for Loops (Control Structures)"
categories: dev
tags: python
---

## Loops (반복문)

- Sometimes, you need to perform code on each item in a list.
  - 가끔은, 배열의 각 항목에 대해 코드를 수행해야 한다.
- This is called iteration, and it can be accomplished with a **while** loop and a counter variable.
  - 이를 반복이라고 부르고, **while** 루프와 카운터 변수를 사용해서 수행할 수 있다.

<br>

- For example:

```python
words = ["hello", "world", "spam", "eggs"]
counter = 0
max_index = len(words) - 1

while counter <= max_index:
   word = words[counter]
   print(word + "!")
   counter = counter + 1
```

<br>

- Result:

```python
>>>
hello!
world!
spam!
eggs!
>>>
```

<br>

> The example above iterates through all items in the list, accesses them using their indices, and prints them with exclamation marks.
>
> 위의 예제는 배열의 모든 항목을 반복하고, 인덱스를 사용해서 엑세스하고, 느낌표와 함께 출력한다.

------

<br>

## for Loop (for 루프)

- Iterating through a list using a **while** loop requires quite a lot of code, so Python provides the **for** loop as a shortcut that accomplishes the same thing.
  - **while** 루프를 사용해서 반복하면 코드가 많이 필요하므로, Python은 동일한 작업을 수행하는 간단한 방법인 **for** 루프를 제공한다.
- The same code from the previous example can be written with a **for** loop, as follows:
  - 앞의 예제와 같은 코드는 다음과 같이 **for** 루프를 사용해서 작성할 수 있다.

```python
words = ["hello", "world", "spam", "eggs"]
for word in words:
   print(word + "!")
```

<br>

- Result:

```python
>>>
hello!
world!
spam!
eggs!
>>>
```

<br>

> The **for** loop in Python is like the **foreach** loop in other languages.
>
> Python의 **for** 루프는 다른 언어의 **foreach**와 유사하다.

------

<br>

## for Loops 02

- The **for** loop is commonly used to repeat some code a certain number of times.
  - **for** 루프는 일반적으로 특정 코드를 특정 회수만큼 반복하는 데 사용된다.
- This is done by combining for loops with **range** objects.
  - 이는 for 루프를 **range** 객체와 결합해서 수행된다.

```python
for i in range(5):
   print("hello!")
```

<br>

- Result:

```python
>>>
hello!
hello!
hello!
hello!
hello!
>>>
```

<br>

> You don't need to call **list** on the **range** object when it is used in a **for** loop, because it isn't being indexed, so a list isn't required.
>
> **range** 객체가 **for** 루프에서 사용될 때, **range** 객체에서 배열을 호출할 필요가 없다.
>
> 인덱싱되지 않기 때문에 배열이 필요하지 않다.

------

<br>

## QUIZ

- Which construct can be used to iterate through a list?
  - if statements
  - **Loops**
  - Variable assignment

<br>

- Fill in the blanks to create a valid for loop.

```python
letters = ['a', 'b', 'c']
for l in letters:
   print(l)
```

<br>

- Fill in the blanks to create a for loop that prints only the even values in the range:

```python
for i in range(0, 20, 2):
   print(i)
```

<br>