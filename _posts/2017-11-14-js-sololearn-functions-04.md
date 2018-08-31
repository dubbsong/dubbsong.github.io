---
layout: post
title: "04. return 문 (Functions)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript return Statement

###### JavaScript return 문

------

<br>

<br>

## Function Return

###### 함수 반환(return)

<br>

- A function can have an optional `return` statement.
  - 함수는 선택적 `return` 문을 가질 수 있다.
- It is used to return a value from the function.
  - 이는 함수에서 값을 반환하는 데 사용된다.

<br>

- This statement is useful when making calculations that require a result.
  - 이 명령문은 결과가 필요한 계산을 할 때 유용하다.

<br>

> When JavaScript reaches a `return` statement, the function stops executing.
>
> JavaScript가 `return` 문에 도달하면, 함수는 실행을 중지한다.

<br>

<br>

- Use the `return` statement to return a value.
  - `return` 문을 사용해서 값을 반환해라.

<br>

- For example, let's calculate the product of two numbers, and return the result.
  - 예를 들어, 두 숫자의 곱을 계산하고, 결과를 반환해보자.

```js
function myFunction(a, b) {
   return a * b;
}

var x = myFunction(5, 6);
// Return value will end up in x
// x equals 30
```

[코드 실행 확인 링크](https://code.sololearn.com/680/#js)

<br>

> If you do not return anything from a function, it will return undefined.
>
> 함수에서 아무것도 반환하지 않으면, undefined를 반환한다.

<br>

<br>

- Another example:

```js
function addNumbers(a, b) {
   var c = a + b;
   return c;
}

document.write(addNumbers(40, 2));	// Outputs 42
```

[코드 실행 확인 링크](https://code.sololearn.com/681/#js)

<br>

> The document.write command outputs the value returned by the function, which is the sum of the two parameters.
>
> document.write 명령은 함수가 반환한 값을 출력한다.

------

<br>

## QUIZ

- When is the "return" statement most frequently needed?
  - "return" 문은 언제 가장 자주 필요한가?

> `When you need to make a calculation and receive the result`
>
> 계산을 하고 결과를 받아야 할 때

<br>

- Where is the "return" statement placed?
  - "return" 문은 어디에 위치하는가?

> `At the end of the function description`
>
> 함수 description의 끝에

<br>

- Please enter the corresponding keyword to have the result of the function below displayed on the screen:
  - 아래 함수의 결과를 화면에 표시하기 위해 해당 키워드를 입력해라.

```js
function substrNumbrs(first, second) {
   var result = first - second;
   return result;
}

document.write(substrNumbrs(10, 5));
```

<br>