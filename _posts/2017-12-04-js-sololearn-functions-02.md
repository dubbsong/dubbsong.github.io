---
layout: post
title: "SoloLearn 번역 - 02. Function Parameters (Functions)"
categories: javascript
tags: JS
---

## Function Parameters (함수 매개변수)

- Functions can take **parameters**.
  - 함수는 **매개변수**를 취할 수 있다.
- Function **parameters** are the names listed in the function's definition.
  - 함수 **매개변수**는 함수의 정의에 나열된 이름이다.

<br>

- Syntax:

```js
functionName(param1, param2, param3) {
   // some code
}
```

<br>

> As with variables, parameters should be given **names**, which are **separated by commas** within the parentheses.
>
> 변수와 마찬가지로, 매개변수는 괄호 안에 **쉼표로 구분된 이름**을 지정해야 한다.

------

<br>

## Using Parameters (매개변수 사용)

- After defining the parameters, you can use them inside the function.
  - 매개변수를 정의한 후에는, 함수 안에서 매개변수를 사용할 수 있다.

```js
function sayHello(name) {
   alert("Hi, " + name);
}

sayHello("David");	// Alerts "Hi, David"
```

<br>

- This function takes in one parameter, which is called **name**.
  - 이 함수는 **name**이라는 하나의 매개변수를 취한다.
- When calling the function, provide the parameter's value (argument) inside the parentheses.
  - 함수를 호출할 때, 괄호 안에 매개변수의 값(인수)을 제공해라.

<br>

> Function **arguments** are the real values passed to (and received by) the function.
>
> 함수 **인수**는 함수에 전달된(그리고 취한) 실제 값이다.

------

<br>

## Function Parameters 02

- You can define a single function, and pass different parameter values (arguments) to it.
  - 단일 함수를 정의하고, 다른 매개변수 값(인수)을 전달할 수 있다.

```js
function sayHello(name) {
   alert("Hi, " + name);
}

sayHello("Sam");
sayHello("Leo");
sayHello("Ralph");
```

<br>

> This will execute the function's code each time for the provided argument.
>
> 위 예제는 제공된 인수에 대해 매번 함수의 코드가 실행될 것이다.

------

<br>

## QUIZ

- What do you need to do to create a parameter?
  - **Write a variable name in the parentheses**
  - Use the "param" keyword
  - Use the "var" keyword

<br>

- When and how is the parameter used?
  - By placing the value before the function call
  - **By calling the function and placing the value in the parentheses**
  - By placing the value before the function name

<br>

- Drag and drop from the options below to declare a function and call it, by passing "Test" as the argument:

```js
function myAlert(txt) {
   alert("Hello " + txt);
}

myAlert("Test");
```

<br>