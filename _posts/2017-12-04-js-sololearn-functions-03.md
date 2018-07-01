---
layout: post
title: "SoloLearn 번역 - 03. Using Multiple Parameters with Functions (Functions)"
categories: javascript
tags: JS
---

## Multiple Parameters

- You can define multiple parameters for a function by **comma-separating** them.
  - 함수에 대해 **콤마로 구분**해서 여러 매개변수를 정의할 수 있다.

```js
function myFunc(x, y) {
   // some code
}
```

<br>

> The example above defines the function **myFunc** to take two parameters.
>
> 위의 예제는 함수 **myFunc**가 두 개의 매개변수를 사용하도록 정의한다.

------

<br>

## Multiple Parameters 02

- The parameters are used within the function's definition.
  - 매개변수는 함수의 정의 내에서 사용된다.

```js
function sayHello(name, age) {
   document.write(name + "is" + age + "years old.");
}
```

------

<br>

## Multiple Parameters 03

- When calling the function, provide the arguments in the same order in which you defined them.
  - 함수를 호출할 때, 정의한 순서와 동일한 순서로 인수를 제공해라.

```js
function sayHello(name, age) {
   document.write(name + "is" + age + "years old.");
}


sayHello("John", 20)	// John is 20 years old.
```

------

<br>

## Multiple Parameters 04

- After defining the function, you can call it as many times as needed.
  - 함수를 정의한 후, 필요한 만큼 여러 번 호출할 수 있다.
- JavaScript functions do not check the number of arguments received.
  - JavaScript 함수는 받은 인수의 수를 확인하지 않는다.

<br>

> If a function is called with missing arguments (fewer than declared), the missing values are set to **undefined**, which indicates that a variable has not been assigned a value.
>
> 누락된 인수(선언된 변수보다 작은)가 있는 함수가 호출되면, 누락된 값은 **undefined**로 설정되며, 이는 변수에 값이 할당되지 않았음을 나타낸다.

> `undefined`: A predefined global variable that is the value of a variable or object that has not been initialized, or of a function that returns no value.

------

<br>

## QUIZ

- What character is used to separate parameters from each other?
  - **,**
  - &
  - :
  - ;

<br>

- What is the output of this code?
  - 5
  - **8**
  - 85

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

<br>

- Fill in the blanks to create a function alerting the sum of the two parameters.

```js
function myFunction(x, y) {
   alert(x + y);
}
```

<br>

- How many times can the declared function be used?
  - Only once
  - Maximum ten
  - **Any**

<br>