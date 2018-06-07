---
layout: post
title: "SoloLearn 번역 - 03. Math Operators (Basic Concepts)"
categories: javascript
tags: JS
---

## Arithmetic Operators (산술 연산자)

- Arithmetic operators perform arithmetic functions on numbers (literals or variables).
  - 산술 연산자는 숫자(문자 또는 변수)에 산술 함수를 수행한다.

![SoloLearn img](/assets/img/sololearn-js-basic concepts-03-01.png)

<br>

- In the example below, the addition operator is used to determine the sum of two numbers.
  - 아래 예제에서, 추가 연산자를 사용해서 두 숫자의 합을 결정한다.

```js
var x = 10 + 5;
document.write(x);

// Outputs 15
```

<br>

- You can add as many numbers or variables together as you want or need to.
  - 원하거나 필요에 따라 숫자 또는 변수를 함께 추가할 수 있다.

```js
var x = 10;
var y = x + 5 + 22 + 45 + 6548;
document.write(y);

// Outputs 6630
```

------

<br>

## Multiplication (곱셈)

- The multiplication operator (*) multiplies one number by the other.
  - 곱셈 연산자(*)는 한 숫자에 다른 숫자를 곱한다.

```js
var x = 10 * 5;
document.write(x);

// Outputs 50
```

------

<br>

## Division (나눗셈)

- The / operator is used to perform division operations:
  - / 연산자는 나누기 연산을 수행하는 데 사용된다.

```js
var x = 100 / 5;
document.write(x);

// Outputs 20
```

------

<br>

## The Modulus (모듈로)

- Modulus (%) operator returns the division remainder (what is left over).
  - 모듈로(%)는 나누기의 나머지(남은 부분)를 반환한다.

```js
var myVariable = 26 % 6;

// myVariable equals 2
```

<br>

> In JavaScript, the modulus operator is used not only on integers, but also on floating point numbers.
>
> JavaScript에서, 모듈로 연산자는 정수뿐만 아니라, 부동 소수점 숫자에도 사용된다.

------

<br>

## Increment & Decrement (증가 & 감소)

#### Increment ++

- The increment operator increments the numeric value of its operand by one.
  - 증가 연산자는 피연산자의 숫자 값을 1씩 증가시킨다.
- If placed before the operand, it returns the incremented value.
  - 만약 피연산자 앞에 놓으면, 증가된 값을 반환한다.
- If placed after the operand, it returns the original value and then increments the operand.
  - 만약 피연산자 뒤에 놓으면, 원래 값을 반환한 다음, 피연산자를 증가시킨다.

<br>

#### Decrement --

- The decrement operator decrements the numeric value of its operand by one.
  - 감소 연산자는 피연산자의 숫자 값을 1씩 감소시킨다.
- If placed before the operand, it returns the decremented value.
  - 만약 피연산자 앞에 놓으면, 감소된 값을 반환한다.
- If placed after the operand, it returns the original value and then decrements the operand.
  - 만약 피연산자 뒤에 놓으면, 원래 값을 반환한 다음, 피연산자를 감소시킨다.

<br>

- Some example:

![SoloLearn img](/assets/img/sololearn-js-basic concepts-03-02.png)

<br>

> As in school mathematics, you can change the order of the arithmetic operations by using parentheses.
>
> 학교 수학과 마찬가지로, 괄호를 사용해서 산술 연산 순서를 변경할 수 있다.

> Example:
>
> var x = (100 + 50) * 3;

------

<br>

## QUIZ

- What will display in the result of the following statements?
  - 5 + 7
  - Test
  - **12**

```js
var test = 5 + 7;
document.write(test);
```

<br>

- What character is used as the multiplication sign?
  - **\***
  - &
  - x

<br>

- Enter the character designated for division:
  - /

<br>

- What is the result of using modulus operator for 38 % 5?
  - 3

<br>

- Increment and decrement are used for:
  - **Adding or subtracting 1 from a number**
  - To change the sign of the number to "+" or "-"
  - To get the remainder of the division of two numbers

<br>