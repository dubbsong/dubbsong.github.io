---
layout: post
title: "SoloLearn 번역 - 01. Variables (Basic Concepts)"
categories: javascript
tags: JS
---

## Variables

- **Variables** are containers for storing data values.
  - **변수**는 데이터 값을 저장하기 위한 컨테이너이다.
- The value of a variable can change throughout the program.
  - 변수의 값은 프로그램 전체에서 변경할 수 있다.
  - `variable`: Defined using the var keyword, variables are used to store data values
- Use the **var** keyword to declare a variable:
  - 변수를 선언하려면 **var** 키워드를 사용해라.
  - `var`: defines a variable

```js
var x = 10;
```

<br>

- In the example above, the value **10** is assigned to the variable x.
  - 위의 예제에서, 10은 변수 x에 할당된다.

<br>

> JavaScript is case sensitive.
>
> JavaScript는 대소문자를 구별한다.
>
> `case-sensitive`: (프로그램이) 대소문자를 구별하는

> For example, the variables *lastName* and *lastname*, are two different variables.
>
> 예를 들어, 변수 *lastName*과 *lastname*은 두 개의 다른 변수이다.

------

<br>

## The Equal Sign (등호)

- In JavaScript, the equal sign (=) is called the **"assignment"** operator, rather than an "equal to" operator.
  - JavaScript에서 등호(=)는 "같다" 연산자가 아니라,  **"할당"** 연산자라고 한다.
- For example, **x = y** will assign the value of **y** to **x**.
  - 예를 들어, **x = y**는 **y**의 값을 **x**에 할당한다.

<br>

> A variable can be declared without a value.
>
> 변수는 값 없이도 선언될 수 있다.

> The value might require some calculation, something that will be provided later, like user input.
>
> 값은 어떤 계산이 필요하며, 유저 입력과 같이 나중에 제공될 것이다.

> A variable declared without a value will have the value **undefined**.
>
> 값 없이 선언된 변수는 값이 **정의되지 않는다**.
>
> `undefined`: A predefined global variable that is the value of a variable or object that has not ben initialized, or of a function that returns no value.

------

<br>

## Using Variables (변수 사용하기)

- Let's assign a value to a variable and output it to the browser.
  - 변수에 값을 할당하고 브라우저에 출력해보자.

```js
var x = 100;
document.write(x);
```

<br>

- Result:

![SoloLearn img](/assets/img/sololearn-js-basic concepts-01-01.png)

<br>

- Using variables is useful in many ways.
  - 변수를 사용하는 것은 여러 면에서 유용하다.
- You might have a thousand lines of code that may include the variable x.
  - 변수 x를 포함할 수 있는 1000줄의 코드가 있을 수 있다.
- When you change the value of x **one time**, it will automatically be changed in **all places** where you used it.
  - x값을 한 번 변경하면, 사용했던 x값이 **모든 장소**에서 자동으로 변경된다.

<br>

> Every written "instruction" is called a **statement**.
>
> 작성한 모든 "명령"은 **작업 명령문**이라고 부른다.

> JavaScript statements are separated by **semicolons**.
>
> JavaScript 문은 **세미콜론**으로 구분된다.

------

<br>

## Naming Variables (변수 네이밍)

- JavaScript variable names are case-sensitive.
  - JavaScript 변수 이름은 대소문자를 구분한다.
- In the example below we changed x to uppercase:
  - 아래 예제에서 x를 대문자로 변경했다.

```js
var x = 100;
document.write(x);
```

<br>

- This code will not result in any output, as x and X are two different variables.
  - x와 X는 서로 다른 두 변수이므로, 아무 결과도 출력하지 않는다.

<br>

#### Naming rules:

- The first character **must be** a letter, an underscore (_), or a dollar sign ($).
  - 첫 번째 문자는 **반드시** 문자, 밑줄(_), 달러 기호($)여야 한다.
- Subsequent characters may be letters, digits, underscores, or dollar signs.
  - 그 후에 오는 문자는 문자, 숫자, 밑줄, 달러 기호일 수 있다.
- Numbers are **not allowed** as the first character.
  - 숫자는 첫 번째 문자로 **사용할 수 없다**.
- Variable names **cannot** include a **mathematical or logical operator** in the name.
  - 변수 이름에 **수학 연산자 또는 논리 연산자를 포함할 수 없다**.
- For instance, *2\*something* or *this\+that*;
  - 예를 들어, *2\*무언가* 또는 *this\+that*
- JavaScript names **must not contain spaces**.
  - JavaScript 이름에는 **공백이 없어야 한다**.

<br>

> Hyphens are not allowed in JavaScript.
>
> 하이픈은 JavaScript에서 허용되지 않는다.

> It is reserved for subtractions.
>
> 하이픈은 뺄셈을 위해 예약되어 있다.

------

<br>

## Naming Variables

- There are some other rules to follow when naming your JavaScript variables:
  - JavaScript 변수를 네이밍 할 때 따라야 할 몇 가지 규칙이 있다.

<br>

1. You **must not** use any **special symbols**, like *my#num, num%*, etc.
   - *my#num*, *num%* 등과 같은 **특수 기호를 사용하면 안 된다**.
2. Be sure that you do not use any of the following JavaScript reserved words.
   - 다음 JavaScript 예약어를 사용하지 마라.

![SoloLearn img](/assets/img/sololearn-js-basic concepts-01-02.png)

<br>

> When you get more familiar with JavaScript, remembering these keywords will be much easier.
>
> JavaScript에 익숙해지면, 이러한 키워드를 기억하는 것이 더 쉽다.

------

<br>

## QUIZ

- Which keyword is used to tell JavaScript that we're going to work with a variable?
  - **var**
  - vrb
  - int
  - variable

<br>

- What is the "=" (equal sign) called in JavaScript?
  - Is equivalent
  - Equal to
  - **Assignment operator**

<br>

- Use the corresponding keyword to complete the statement.

```js
var my_variable = 32;
```

<br>

- What characters can be used to start a variable? (Select all that apply)
  - **Letters**
  - Numbers
  - Mathematical operators
  - **Underscore sign (_)**

<br>

- What characters cannot be used in variable names?
  - Letters
  - Numbers
  - Underscore sign
  - **Special symbols (%, #, etc.)**

<br>