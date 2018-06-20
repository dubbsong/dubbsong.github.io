---
layout: post
title: "SoloLearn 번역 - 01. User-Defined Functions (Functions)"
categories: javascript
tags: JS
---

## JavaScript Functions (JS 함수)

- A JavaScript **function** is a block of code designed to perform a particular task.
  - JavaScript **함수**는 특정한 작업을 수행하도록 설계된 코드 블록이다.

<br>

#### The main advantages of using function:

###### 함수 사용의 주요 이점:

> Code **reuse**: Define the code once, and use it many times.
>
> 코드 **재사용**: 코드를 한 번 정의하고, 여러 번 사용해라.

<br>

- Use the same code many times with different **arguments**, to produce different results.
  - 다른 **인수**를 사용해서 동일한 코드를 여러 번 사용하면, 다른 결과가 나타난다.

<br>

> A JavaScript function is executed when "something" invokes, or calls, it.
>
> JavaScript 함수는 "무언가"가 호출을 바라거나, 호출할 때 실행된다.

------

<br>

## Defining a Function (함수 정의)

- To define a JavaScript function, use the **function** keyword, followed by a **name**, followed by a set of **parentheses ()**.
  - JavaScript 함수를 정의하려면, **function** 키워드를 사용하고, **이름** 뒤에 **괄호 ()** 세트를 사용해라.

<br>

- The code to be executed by the function is placed inside curly brackets {}.
  - 함수에 의해 실행될 코드는 중괄호 {} 안에 위치한다.

```js
function name() {
   // code to be executed
}
```

<br>

> Function names can contain letters, digits, underscores, and dollar signs (same rules as variables).
>
> 함수 이름에는 문자, 숫자, 밑줄, 달러 기호(변수와 동일한 규칙)가 포함될 수 있다.

------

<br>

## Calling a Function (함수 호출)

- To execute the function, you need to call it.
  - 함수를 실행하려면, 호출해야 한다.
- To call a function, start with the name of the function, then follow it with the arguments in parentheses.
  - 함수를 호출하려면, 함수의 이름으로 시작한 다음, 괄호 안의 인수를 사용해라.

<br>

- Example:

```js
function myFunction() {
   alert("Calling a Function!");
}

myFunction();	// Alerts "Calling a Function!"
```

<br>

> Always remember to end the statement with a **semicolon** after calling the function.
>
> 함수를 호출한 후에는 항상 **세미콜론**으로 문장을 끝내는 것을 기억해라.

------

<br>

## Calling Functions

- Once the function is defined, JavaScript allows you to call it as many times as you want to.
  - 함수가 정의되면, JavaScript는 원하는 만큼 여러 번 호출할 수 있다.

```js
function myFunction() {
   alert("Alert box!");
}

myFunction();	// "Alert box!"

// some other code

myFunction();	// "Alert box!"
```

------

<br>

## QUIZ

- What is a function?
  - Profession
  - **A certain block of code that can be reused over and over again**
  - Arithmetical term

<br>

- Add the corresponding keyword and symbols to create a function named "test".

```js
function test() {
   /* some code */
}
```

<br>

- Fill in the blanks to define and call the "hello" function.

```js
function hello() {
   alert("Hi there");
}

hello();
```

<br>

- How many times can the function be executed inside a web page?
  - **As many as needed**
  - 1024
  - 2

<br>