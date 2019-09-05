---
layout: post
title: "(Functions & Modules 01) 코드 재사용"
categories: dev
tags: python
---

###### [SoloLearn](https://www.sololearn.com) Python 번역

<br>

- `Code reuse` is a very important part of programming in any language.
  - `코드 재사용`은 프로그래밍의 아주 중요한 부분이다.
- Increasing code size makes it harder to maintain.
  - 코드 크기가 커지면 유지 관리가 어려워진다.
- For a large programming project to be successful, it is essential to abide by the `Don't Repeat Yourself`, or `DRY`, principle.
  - 대규모 프로그래밍 프로젝트를 성공하려면, `DRY(중복배제)` 원칙을 준수하는 것이 중요하다.
- We've already looked at one way of doing this: by using loops.
  - 우리는 이미 loop를 사용하는 방법 중 하나를 살펴보았다.
- In this module, we will explore two more: functions and modules.
  - 함수와 모듈을 더 살펴보자.

<br>

> Bad, repetitive code is said to abide by the `WET` principle, which stands for `Write Everything Twice`, or `We Enjoy Typing`.
>
> 나쁘고 반복적인 코드는 `WET` 원칙을 준수한다고 한다.
>
> `WET`은 `Write Everything Twice` 또는 `We Enjoy Typing`의 약자이다.

<br>

## Functions

###### 함수

<br>

- You've already used `functions` in previous lessons.
  - 이전 레슨에서 이미 `함수`를 사용했다.
- Any statement that consists of a word followed by information in `parentheses` is a function call.
  - 단어 뒤 `괄호` 안의 정보로 구성되는 모든 명령문은 함수 호출이다.
- Here are some examples that you've already seen:
  - 다음 예제는 이미 보았었다.

```python
print("Hello World")
range(2, 20)
str(12)
range(10, 20, 3)
```

<br>

> The words in front of the parentheses are function `names`, and the comma-separated values inside the parentheses are function `arguments`.
>
> 괄호 앞의 단어는 함수 `이름`이다.
>
> 괄호 안의 쉼표로 구분된 값은 함수 `인수`이다.

<br>

<br>

#### QUIZ

- Following the DRY principle makes the code:
  - DRY 원칙에 따라 코드를 ...

> `easier to maintain`
>
> 보다 쉽게 유지 관리할 수 있다

<br>

- How many arguments are in this function call?
  - 이 함수 호출에는 몇 개의 인수가 있는가?

```python
range(0, 100, 5)
```

> `3`

<br>

<br>