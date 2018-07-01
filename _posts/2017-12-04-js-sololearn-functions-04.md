```
layout: post
title: "SoloLearn 번역 - 04. The return Statement (Functions)"
categories: javascript
tags: JS
```

## Function Return (함수 반환)

- A function can have an optional **return** statement.
  - 함수는 선택적 **return** 문을 가질 수 있다.
- It is used to return a value from the function.
  - 함수에서 값을 반환하는 데 사용된다.
- This statement is useful when making calculations that require a result.
  - 이 명령문은 결과가 필요한 계산을 할 때 유용하다.

<br>

> When JavaScript reaches a **return** statement, the function stops executing.
>
> JavaScript가 **return** 문에 도달하면, 함수는 실행을 멈춘다.

------

<br>

## Function Return 02

- Use the **return** statement to return a value.
  - **return** 문을 사용해서 값을 반환해라.
- For example, let's calculate the product of two numbers, and return the result.
  - 예를 들어, 두 숫자의 곱을 계산하고, 결과를 반환해라.

```js
function myFunction(a, b) {
   return a * b;
}


var x = myFunction(5, 6);	// x equals 30
```

<br>

> If you do not return anything from a function, it will return **undefined**.
>
> 함수에서 아무것도 반환하지 않으면, **undefined**를 반환한다.

------

<br>

## Function Return 03

- Another example:

```js
function addNumbers(a, b) {
   var c = a + b;
   return c;
}


document.write(addNumbers(40, 2));	// 42
```

<br>

> The document.write command outputs the value returned by the function, which is the sum of the two parameters.
>
> document.write 명령은 두 매개변수의 합계인, 함수가 반환한 값을 출력한다.

------

<br>

## QUIZ

- When is the "return" statement most frequently needed?
  - When you need to input data
  - **When you need to make a calculation and receive the result**
    - 계산을 하고 결과를 받아야 할 때
  - When you need to add a pop-up window to the screen

<br>

- Where is the "return" statement placed?
  - Outside the curly braces
  - At the beginning of the function description
  - **At the of the function description**

<br>

- Please enter the corresponding keyword to have the result of the function below displayed on the screen:

```js
function substrNumbrs(first, second) {
   var result = first - second;
   return result;
}


document.write(substrNumbrs(10, 5));
```

<br>