---
layout: post
title: "(번역) 함수 선언식 vs. 함수 표현식"
categories: js
---

###### [Mandeep Singh](https://medium.com/@mandeep1012/function-declarations-vs-function-expressions-b43646042052) 포스팅 번역

<br>

## Function Declarations vs. Function Expressions

###### 함수 선언식 vs. 함수 표현식

<br>

- The function statement declares a function.
  - 함수 명령문은 함수를 선언한다.
- A declared function is "saved for later use", and will be executed later, when it is invoked.
  - 선언된 함수는 "나중에 사용하기 위해 저장"하고, 호출될 때 실행된다.
- Just as Variable Declarations must start with "var", Function Declarations must begin with "function".
  - 변수 선언이 "var"로 시작하는 것처럼, 함수 선언식은 "function"으로 시작해야 한다.

```js
function bar() {
  return 3;
}
```

<br>

### What is a Function Expression?

###### 함수 표현식은 무엇인가?

<br>

- A JavaScript function can also be defined using an `expression`.
  - JS 함수는 `표현식`을 사용해서 정의할 수도 있다.
- A function expression can be stored in a variable:
  - 함수 표현식은 변수에 저장될 수 있다.

<br>

### Function Expression vs. Function Statement

###### 함수 표현식 vs. 함수 명령문

<br>

- Example: Function Expression
  - 함수 표현식의 예

```js
alert(foo());	// Error! foo wasn't loaded yet
var foo = function() { return 5; }
```

<br>

- Example: Function Declaration
  - 함수 선언식의 예

```js
alert(foo());	// Alert 5. 선언은 모든 코드가 실행되기 전에 로딩된다.
function foo() { return 5; }
```

<br>

- `Function declarations` load before any code is executed while `Function expressions` load only when the interpreter reaches that line of code.
  - `함수 선언식`은 모든 코드가 실행되기 전에 로딩된다.
  - `함수 표현식`은 interpreter가 해당 코드 라인에 도달할 때 로딩된다.
- Similar to the `var` statement, function declarations are hoisted to the top of other code.
  - `var` 명령문과 마찬가지로, 함수 선언식은 코드의 맨 위로 호이스팅(hoisting) 된다.
- Function expressions aren't hoisted, which allows them to retain a copy of the local variables from the scope where they were defined.
  - 함수 표현식은 호이스팅 되지 않는다.
  - 그러므로 정의된 범위의 로컬 변수 복사본을 유지할 수 있다.

<br>

### Benefits of Function Expressions

###### 함수 표현식의 이점

<br>

- There are several different ways that function expressions become more useful than function declarations.
  - 함수 표현식이 함수 선언식보다 더 유용하게 사용되는 몇 가지 방법이 있다.

<br>

1. As closures
   - 클로저로 사용될 때
2. As arguments to other functions
   - 다른 함수에 인수로 사용될 때
3. As Immediately Invoked Function Expressions (IIFE)
   - IIFE로 사용될 때

<br>