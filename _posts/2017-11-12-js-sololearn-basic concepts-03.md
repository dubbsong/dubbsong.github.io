---
layout: post
title: "03. 수학 연산자 (Basic Concepts)"
categories: dev
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript Math Operators

###### JavaScript 수학 연산자

------

<br>

<br>

## Arithmetic Operators

###### 산술 연산자

<br>

- Arithmetic operators perform arithmetic functions on numbers (literals or variables).
  - 산술 연산자는 숫자(문자열 또는 변수)에 산술 기능을 수행한다.

![sololearn img](/assets/img/sololearn-js-basic concepts-03-01.png)

<br>

- In the example below, the addition operator is used to determine the sum of two numbers.
  - 아래 예제에서는, 더하기 연산자를 사용해서 두 숫자의 합을 결정한다.

```js
var x = 10 + 5;
document.write(x);

// Output 15
```

[코드 실행 확인 링크](https://code.sololearn.com/651/#js)

<br>

- You can add as many numbers or variables together as you want or need to.
  - 필요에 따라 숫자 또는 변수를 추가할 수 있다.

```js
var x = 10;
var y = x + 5 + 22 + 45 + 6548;
document.write(y);

// Output 6630
```

[코드 실행 확인 링크](https://code.sololearn.com/652/#js)

------

<br>

## Multiplication

###### 곱셈 연산자

<br>

- The multiplication operator (*) multiplies one number by the other.
  - 곱셈 연산자(*)는 한 숫자에 다른 숫자를 곱한다.

```js
var x = 10 * 5;
document.write(x);

// Output 50
```

[코드 실행 확인 링크](https://code.sololearn.com/653/#js)

------

<br>

## Division

###### 나눗셈 연산자

<br>

- The / operator is used to perform division operations:
  - / 연산자는 나눗기 연산을 수행하는 데 사용된다.

```js
var x = 100 / 5;
document.write(x);

// Output 20
```

[코드 실행 확인 링크](https://code.sololearn.com/654/#js)

------

<br>

## The Modulus

###### Modulus(계수) 연산자

<br>

- Modulus (%) operator returns returns the division remainder (what is left over).
  - Modulus(%) 연산자는 나누기 나머지(남은 부분)를 반환한다.

```js
var myVariable = 26 % 6;

// myVariable equals 2
```

[코드 실행 확인 링크](https://code.sololearn.com/655/#js)

<br>

> In JavaScript, the modulus operator is used not only on integers, but also on floating point numbers.
>
> JavaScript에서는, modulus 연산자가 정수뿐만 아니라, 부동 소수점 숫자에도 사용된다.

------

<br>

## Increment & Decrement

###### 증가 & 감소

<br>

#### Increment ++

- The increment operator increments the numeric value of its operand by one.
  - 증가 연산자는 피연산자의 숫자 값을 1씩 증가시킨다.
- If placed before the operand, it returns the incremented value.
  - 피연산자 앞에 놓으면, 증가된 값을 반환한다.
- If placed after the operand, it returns the original value and then increments the operand.
  - 피연산자 뒤에 놓으면, 원래 값을 반환한 다음 피연산자를 증가시킨다.

<br>

#### Decrement --

- The decrement operator decrements the numeric value of its operand by one.
  - 감소 연산자는 피연산자의 숫자 값을 1씩 감소시킨다.
- If placed before the operand, it returns the decremented value.
  - 피연산자 앞에 놓으면, 감소된 값을 반환한다.
- If placed after the operand, it returns the original value and then decrements the operand.
  - 피연산자 뒤에 놓으면, 원래 값을 반환한 다음 피연산자를 감소시킨다.

<br>

- Some examples:

![sololearn img](/assets/img/sololearn-js-basic concepts-03-02.png)

<br>

> As in school mathematics, you can change the order of the arithmetic operations by using parentheses.
>
> 수학과 마찬가지로, 괄호를 사용해서 산술 연산 순서를 변경할 수 있다.

> Example: var x = (100 + 50) * 3;

------

<br>

## QUIZ

- What will display in the result of the following statements?
  - 다음 명령문의 결과는 무엇이 표시되는가?

```js
var test = 5 + 7;
document.write(test);
```

> `12`

<br>

- What character is used as the multiplication sign?
  - 곱셈 기호로 어떤 문자가 사용되는가?

> `*`

<br>

- Enter the character designated for division:
  - 나눗셈을 위한 지정된 문자를 입력해라.

> `/`

<br>

- What is the result of using modulus operator for 38 % 5?
  - 38 % 5에 대해 modulus 연산자를 사용한 결과는 무엇인가?

> `3`

<br>

- Increment and decrement are used for:
  - 증가와 감소는 ...로 사용된다.

> `Adding or subtracting 1 from a number`
>
> 숫자에서 1을 더하거나 빼기

<br>