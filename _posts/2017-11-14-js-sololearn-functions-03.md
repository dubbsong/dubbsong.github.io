---
layout: post
title: "03. 함수에 여러 매개변수 사용하기 (Functions)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# Using Multiple Parameters with Functions

###### 함수에 여러 매개변수 사용하기

------

<br>

<br>

## Multiple Parameters

###### 여려 매개변수

<br>

- You can define multiple parameters for a function by `comma-separating` them.
  - 함수에 대해 여러 매개변수를 `쉼표로 구분해서` 정의할 수 있다.

```js
function myFunc(x, y) {
   // some code
}
```

<br>

> The example above defines the function `myFunc` to take two parameters.
>
> 위의 예제는 `myFunc` 함수가 두 개의 매개변수를 가지도록 정의한다.

<br>

<br>

- The parameters are used within the function's definition.
  - 매개변수는 함수의 정의 내에서 사용된다.

```js
function sayHello(name, age) {
   document.write(name + " is " + age + " years old.");
}
```

<br>

> Function parameters are the names listed in the function definition.
>
> 함수 매개변수는 함수 정의에 나열된 이름이다.

<br>

<br>

- When calling the function, provide the arguments in the same order in which you defined them.
  - 함수를 호출할 때, 정의한 순서와 동일한 순서로 인수를 제공해라.

```js
function sayHello(name, age) {
   document.write(name + " is " + age + " years old.");
}
```

[코드 실행 확인 링크](https://code.sololearn.com/679/#js)

<br>

> If you pass more arguments than are defined, they will be assigned to an array called arguments.
>
> 정의된 것보다 많은 인수를 전달하면, 인수라는 배열에 할당된다.

> They can be used like this: arguments[0], arguments[1], etc
>
> arguments[0], arguments[1] 등과 같이 사용할 수 있다.

<br>

<br>

- After defining the function, you can call it as many times as needed.
  - 함수를 정의한 후, 필요한 만큼 여러 번 호출할 수 있다.
- JavaScript functions do not check the number of arguments received.
  - JavaScript 함수는 받은 인수의 수를 확인하지 않는다.

<br>

> If a function is called with missing arguments (fewer than declared), the missing values are set to undefined, which indicates that a variable has not been assigned a value.
>
> 누락된 인수가 있는 함수가 호출되면, 누락된 값은 undefined로 설정되며, 이는 변수에 값이 할당되지 않았음을 나타낸다.

> `undefined`: A predefined global variable that is the value of a variable or object that has not been initialized, or of a function that returns no value. (초기화되지 않은 변수나 객체의 값인 미리 정의된 전역 변수, 값을 반환하지 않는 함수의 미리 정의된 전역 변수)

------

<br>

## QUIZ

- What character is used to separate parameters from each other?
  - 각 매개변수를 구분하는 데 사용되는 문자는 무엇인가?

> `,`

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```js
function test(x, y) {
   if (x > y) {
      document.write(x);
   } else {
      document.write(y);
   }
}

test(5, 8);
```

> `8`

<br>

- Fill in the blanks to create a function alerting the sum of the two parameters.
  - 두 매개변수의 합을 alert 하는 함수를 작성해라.

```js
function myFunction(x, y) {
   alert(x + y);
}
```

<br>

- How many times can the declared function be used?
  - 선언된 함수를 몇 번 사용할 수 있는가?

> `Any`

<br>