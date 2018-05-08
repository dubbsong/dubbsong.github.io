---
layout: post
title: "SoloLearn - 13. Module 2 Quiz (Control Structures)"
categories: dev
tags: python
---

- What is the output of this code?

```python
list = [1, 1, 2, 3, 5, 8, 13]
print(list[list[4]])

8
```

<br>

- What does this code do?
  - Print all the odd numbers between 1 and 9
  - Print all the even numbers between 0 and 8
  - **Print all the even numbers between 2 and 10**

```python
for i in range(10):
   if not i % 2 == 0:
      print(i + 1)
```

<br>

- How many lines will this code print?
  - **0**
  - 1
  - Infinitely many

```python
while False:
   print("Looping...")
```

<br>

- Fill in the blanks to print the first element of the list, if it contains even number of elements.

```python
list = [1, 2, 3, 4]
if len(list) % 2 == 0:
   print(list[0])
```

<br>

- What does this code output?

```python
letters = ['x', 'y', 'z']
letters.insert(1, 'w')
print(letters[2])

y
```

<br>

- Fill in the blanks to iterate over the list using a for loop and print its values.

```python
list = [1, 2, 3]
	for var in list:
      print(var)
```

<br>