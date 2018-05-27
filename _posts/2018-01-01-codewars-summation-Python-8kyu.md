---
layout: post
title: "summation.py (8kyu)"
categories: codewars
tags: Algorithm
---

#### 반복문(for loop) + 기본 수학(basic math) + 메소드(method) 활용 알고리즘 문제

<br>

## problem

Write a program

that finds the `summation` of every number

between `1` and `n`.

<br>

The number will always be a positive integer greater than 0.

<br>

## solution 01

```python
def summation(n):
   return n * (n + 1) / 2


print(summation(10))	# 55
print(summation(100))	# 5050
```

<br>

## solution 02

```python
def summation(n):
   result = 0
   
   for i in range(0, n + 1):
      result += i
	return result


print(summation(10))	# 55
print(summation(100))	# 5050
```

> `range()` 메소드
>
> 기본적으로 0부터 시작해서 1씩 증가하고,
>
> 지정된 숫자로 끝나는 일련의 숫자 배열을 반환한다.

<br>

## solution 03

```python
def summation(n):
   return sum(range(0, n + 1))


print(summation(10))	# 55
print(summation(100))	# 5050
```

> `sum()` 메소드
>
> 반복 가능한 모든 항목의 합을 반환한다.

<br>

## solution 04

```python
def summation(n):
   return sum(xrange(0, n + 1))


print(summation(10))	# 55
print(summation(100))	# 5050
```

> `xrange()` 메소드
>
> `range()` 메소드와 비슷하지만, 배열 대신 객체를 반환한다.

<br>