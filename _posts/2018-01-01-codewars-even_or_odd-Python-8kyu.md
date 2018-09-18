---
layout: post
title: "even_or_odd.py (8kyu)"
categories: codewars
tags: Algorithm
---

#### 조건문(if) 활용 알고리즘 문제

<br>

## problem

Create a function

that takes an integer as an argument

and returns '`Even`' for even numbers

or '`Odd`' for odd numbers.

<br>

## solution 01

```python
def even_or_odd(number):
   if number % 2 == 0:
      return 'Even'
   else:
      return 'Odd'
   

print(even_or_odd(1))	# Odd
print(even_or_odd(2))	# Even
```

<br>

## solution 02

```python
def even_or_odd(number):
   if number % 2:
      return 'Odd'
   else:
      return 'Even'
   
   
print(even_or_odd(1))	# Odd
print(even_or_odd(2))	# Even
```

<br>

## solution 03

```python
def even_or_odd(number):
   if number % 2:
      return 'Odd'
   return 'Even'


print(even_or_odd(1))	# Odd
print(even_or_odd(2))	# Even
```

<br>

## solution 04

```python
def even_or_odd(number):
   return 'Odd' if number % 2 else 'Even'


print(even_or_odd(1))	# Odd
print(even_or_odd(2))	# Even
```

<br>

## solution 05

```python
even_or_odd = lambda number: 'Odd' if number % 2 else 'Even'


print(even_or_odd(1))	# Odd
print(even_or_odd(2))	# Even
```

<br>

