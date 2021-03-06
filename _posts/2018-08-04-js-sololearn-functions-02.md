---
layout: post
title: "(Functions 02) 함수의 매개변수"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## Function Parameters

###### 함수의 매개변수

<br>

- Functions can take `parameters`.
  - 함수는 `매개변수`를 사용할 수 있다.
- Function `parameters` are the names listed in the function's definition.
  - 함수의 `매개변수`는, 함수의 정의에 나열된 이름이다.

```js
functionName(param1, param2, param3) {
   // some code
}
```

<br>

> As with variables, parameters should be given `names`, which are `separated by commas` within the parentheses.
>
> 변수와 마찬가지로, 매개변수는 괄호 내에 `쉼표로 구분된 이름`을 지정해야 한다.
>
> 변수와 마찬가지로, 매개변수는 `이름`을 지정해야 하고, `쉼표로 구분`된다.

------

<br>

## Using Parameters

###### 매개변수 사용하기

<br>

- After defining the parameters, you can use them inside the function.
  - 매개변수를 정의한 후, 함수 내에서 매개변수를 사용할 수 있다.

```js
function sayHello(name) {
   alert("Hi, " + name);
}

sayHello("Leo");	// Hi, Leo
```

[코드 실행 확인](https://code.sololearn.com/677/#js)

<br>

- This function takes in one parameter, which is called `name`.
  - 이 함수는 `name`이라는 하나의 매개변수를 사용한다.
- When calling the function, provide the parameter's value (argument) inside the parentheses.
  - 함수를 호출할 때, 매개변수의 값(인수)을 괄호 내에 제공한다.

<br>

> Function `arguments` are the real values passed to (and received by) the function.
>
> 함수의 `인수`는 함수에 전달된 실제 값이다.

------

<br>

## Function Parameters

###### 함수의 매개변수

<br>

- You can define a single function, and pass different parameter values (arguments) to it.
  - 하나의 함수를 정의해서, 서로 다른 매개변수 값(인수)을 전달할 수 있다.

```js
function sayHello(name) {
   alert("Hi, " + name);
}

sayHello("Leo");	// Hi, Leo
sayHello("Sam");	// Hi, Sam
sayHello("Ralph");	// Hi, Ralph
```

[코드 실행 확인](https://code.sololearn.com/678/#js)

<br>

> This will execute the function's code each time for the provided argument.
>
> 이는 제공된 인수에 대해 매번 함수의 코드가 실행된다.

------

<br>

## QUIZ

- What do you need to do to create a parameter?
  - 매개변수를 생성하려면 무엇을 해야 하는가?

> `Write a variable name in the parentheses`
>
> 괄호 내에 변수 이름을 작성한다

<br>

- When and how is the parameter used?
  - 매개변수는 언제 어떻게 사용되는가?

> `By calling the function and placing the value in the parentheses`
>
> 값을 괄호 내에 위치시키고, 함수를 호출함으로써 사용된다

<br>

- Drag and drop from the options below to declare a function and call it, by passing "Test" as the argument:
  - "Test"를 인수로 전달해서, 함수를 선언하고 호출해라.

```js
function myAlert(txt) {
   alert("Hello " + txt);
}

myAlert("Test");	// Hello Test
```

<br>