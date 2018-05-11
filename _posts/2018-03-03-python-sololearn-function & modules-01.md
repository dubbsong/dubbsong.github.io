---
layout: post
title: "SoloLearn 번역 - 01. Code Reuse (Function & Modules)"
categories: dev
tags: python
---

## Reusing Code (코드 재사용)

- **Code reuse** is a very important part of programming in any language.
  - **코드 재사용**은 어느 프로그래밍 언어에서나 매우 중요한 부분이다.
- Increasing code size makes it harder to maintain.
  - 코드가 많아지면 유지 관리가 더 어려워진다.
- For a large programming project to be successful, it is essential to abide by the **Don't Repeat Yourself**, or **DRY**, principle.
  - 대규모 프로그래밍 프로젝트가 성공하려면, **Don't Repeat Yourself** 또는 **DRY** 원칙을 준수하는 것이 필수다.
- We've already looked at one way of doing this: by using loops.
  - 우리는 이미 이렇게 하는 한 가지 방법을 살펴보았다: 루프를 사용하는 방법을.
- In this module, we will explore two more: functions and modules.
  - 이 모듈에서는, 두 가지 방법을 더 살펴보겠다: 함수와 모듈을 사용하는 방법을.

<br>

> Bad, repetitive code is said to abide by the **WET** principle, which stands for **Write Everything Twice**, or **We Enjoy Typing**.
>
> 잘못되었거나, 반복적인 코드는 **Write Everything Twice** 또는 **We Enjoy Typing**을 나타내는 **WET** 원칙을 준수한다고 한다.

------

<br>

## Functions (함수)

- You've already used **functions** in previous lessons.
  - 우리는 이미 이전 강의에서 함수를 사용했다.
- Any statement that consists of a word followed by information in **parentheses** is a function call.
  - **괄호** 안에 정보가 오는 단어로 구성된 모든 명령문은 함수 호출이다.
- Here are some examples that you've already seen:
  - 여기에 이미 봤던 몇 가지 예가 있다.

```python
print("Hello world!")
range(2, 20)
str(12)
range(10, 20, 3)
```

<br>

> The words in front of the parentheses are function **names**, and the comma-separated values inside the parentheses are function **arguments**.
>
> 괄호 앞의 단어는 함수 **이름**이고, 괄호 안의 쉼표로 구분된 값은 함수 **인수**이다.

------

<br>

## QUIZ

- Following the DRY principle makes the code:
  - **easier to maintain**
  - loop forever
  - bad and repetitive

<br>

- How many arguments are in this function call?

```python
range(0, 100, 5)

3
```

<br>