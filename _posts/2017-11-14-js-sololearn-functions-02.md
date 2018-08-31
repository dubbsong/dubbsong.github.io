---
layout: post
title: "02. 함수 매개변수 (Functions)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript Function Parameters

###### JavaScript 함수 매개변수

<br>

- Functions can take `parameters`.
  - 함수는 `매개변수`를 취할 수 있다.
- Function `parameters` are the names listed in the function's definition.
  - 함수 `매개변수`는 함수의 정의에 나열된 이름이다.

<br>

- Syntax:

```js
function Name(param1, param2, param3) {
   // some code
}
```

<br>

> As with variables, parameters should be given `names`, which are `separated by commas` within the parentheses.
>
> 변수와 마찬가지로, 매개변수는 괄호 내에 `쉼표로 구분된` `이름`을 지정해야 한다.

------

<br>

## Using Parameters

###### 매개변수 사용하기

<br>

- After defining the parameters, you can use them inside the function.
  - 매개변수를 정의한 후에는, 함수 내에서 매개변수를 사용할 수 있다.

```js
function sayHello(name) {
   alert("Hi, " + name);
}

sayHello("David");	// Alerts "Hi, David"
```

[코드 실행 확인 링크](https://code.sololearn.com/677/#js)

<br>

- This function takes in one parameter, which is called `name`.
  - 이 함수는 `name`이라는 하나의 매개변수를 사용한다.
- When calling the function, provide the parameter's value (argument) inside the parentheses.
  - 함수를 호출할 때, 괄호 내에 매개변수의 값(인수)을 제공해라.

<br>

> Function `arguments` are the real values passed to (and received by) the function.
>
> 함수 `인수`는 함수에 전달된 실제 값이다.

------

<br>

## Function Parameters

###### 함수 매개변수

<br>

- You can define a single function, and pass different parameter values (arguments) to it.
  - 하나의 함수를 정의하고, 다른 매개변수 값(인수)을 전달할 수 있다.

```js
function sayHello(name) {
   alert("Hi, " + name);
}

sayHello("David");
sayHello("Sarah");
sayHello("John");
```

[코드 실행 확인 링크](https://code.sololearn.com/678/#js)

<br>

> This will execute the function's code each time for the provided argument.
>
> 이는 제공된 인수에 대해 매번 함수의 코드가 실행된다.

------

<br>

## QUIZ

- What do you need to do to create a parameter?
  - 매개변수를 만들려면 무엇이 필요한가?

> `Write a variable name in the parentheses`
>
> 변수 이름을 괄호 안에 작성한다

<br>

- When and how is the parameter used?
  - 매개변수는 언제 어떻게 사용되는가?

> `By calling the function and placing the value in the parentheses`
>
> 함수를 호출하고, 괄호 안에 값을 위치시켜서

<br>

- Drag and drop from the options below to declare a function and call it, by passing "Test" as the argument:
  - "Test"를 인수로 전달해서 함수를 선언하고 호출해라.

```js
function myAlert(txt) {
   alert("Hello " + txt);
}

myAlert("Test");
```

<br>