---
layout: post
title: "(8kyu.py) Even or Odd"
categories: codewars
---

<br>

## problem

- Create a function that takes an integer as an argument and returns `Even` for even numbers or `Odd` for odd numbers.
  - 정수를 인수로 가져오고, 짝수의 경우 `Even`을, 홀수의 경우 `Odd`를 반환하는 함수를 생성해라.

------

<br>

### solution 01

```python
def even_or_odd(number):
   if number % 2 == 0:
      return 'Even'
   else:
      return 'Odd'
   
   
even_or_odd(2);	// Even
even_or_odd(1);	// Odd
```

<br>

### solution 02

```python
def even_or_odd(number):
   return 'Even' if number % 2 == 0 else 'Odd'


even_or_odd(2);	// Even
even_or_odd(1);	// Odd
```

<br>

### solution 03

```python
def even_or_odd(number):
   return 'Odd' if number % 2 else 'Even'


even_or_odd(2);	// Even
even_or_odd(1);	// Odd
```

<br>

### solution 04

```python
def even_or_odd(number):
   return ['Even', 'Odd'][number % 2]


even_or_odd(2);	// Even
even_or_odd(1);	// Odd
```

<br>

### solution 05

```python
even_or_odd = lambda number: 'Odd' if number % 2 else 'Even'


even_or_odd(2);	// Even
even_or_odd(1);	// Odd
```

------

<br>