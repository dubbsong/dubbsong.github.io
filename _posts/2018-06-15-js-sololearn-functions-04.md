---
layout: post
title: "(Functions 04) return 문"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## Function Return

###### 함수 반환하기

<br>

- A function can have an optional `return` statement.
  - 함수는 선택적 `return` 문을 가질 수 있다.
- It is used to return a value from the function.
  - 이는 함수에서 값을 반환하는 데 사용된다.

<br>

- This statement is useful when making calculations that require a result.
  - return 문(statement)은 결과가 필요한 계산을 할 때 유용하다.

<br>

> When JavaScript reaches a `return` statement, the function stops executing.
>
> JavaScript가 `return` 문에 도달하면, 함수는 실행을 중단한다.

<br>

<br>

- Use the `return` statement to return a value.
  - `return` 문을 사용해서 값을 반환한다.

<br>

- For example, let's calculate the product of two numbers, and return the result.
  - 두 숫자의 곱을 계산하고, 결과를 반환해보자.

```js
function myFunction(a, b) {
   return a * b;
}

var x = myFunction(5, 6);

document.write(x);	// 30
```

[코드 실행 확인](https://code.sololearn.com/680/#js)

<br>

> If you do not return anything from a function, it will return `undefined`.
>
> 함수에서 아무것도 반환하지 않으면 `undefined`를 반환한다.

<br>

<br>

- Another example:

```js
function addNumbers(a, b) {
   var c = a + b;
   return c;
}

document.write(addNumbers(40, 2));	// 42
```

[코드 실행 확인](https://code.sololearn.com/681/#js)

<br>

> The document.write command outputs the value returned by the function, which is the sum of the two parameters.
>
> document.write 명령은 함수가 반환한 값(두 매개변수의 합)을 출력한다.

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
> 함수 서술의 끝에

<br>