---
layout: post
title: "(번역) 함수 선언식 vs 함수 표현식"
categories: js
---

###### [Ravi Roshan](https://medium.com/@raviroshan.talk/javascript-function-declaration-vs-expression-f5873b8c7b38) 포스팅 번역

<br>

## Function Declaration vs Expression

###### 함수 선언식 vs 함수 표현식

<br>

- Functions are considered as `First Class citizen in JavaScript` and it is really important to be clear with the concept of creating function in JS.
  - JS에서 함수는 `1급 객체`로 간주되므로, 함수 생성의 개념은 아주 중요하다.

![img](/assets/img/ravi-roshan-01.png)

<br>

- Unlike other programming languages, we can create function in JavaScript using 3 distinct ways:
  - 다른 프로그래밍 언어와는 달리, JS는 3가지 방법으로 함수를 생성할 수 있다.

<br>

1. `Function Declaration`
   - 함수 선언식
2. `Function Expression`
   - 함수 표현식
3. `Named Function Expression`
   - named 함수 표현식

<br>

#### Function Declaration

###### 함수 선언식

<br>

```js
function [name](param1, param2, ...param3) {
  // 함수 Body & Logic
}
```

<br>

- In this case, we prefix `[function keyword]` before respective `[function name]`.
  - 함수 선언식의 경우, 각 `[함수 이름]` 앞에 `[function 키워드]`를 놓는다.
- One major advantage of this approach is that the complete function is [Hoisted](https://medium.freecodecamp.org/what-is-variable-hoisting-differentiating-between-var-let-and-const-in-es6-f1a70bb43d).
  - 함수 선언식의 큰 장점은, 함수가 호이스팅(hoisting)된다는 것이다.
- **Because of that, we can execute the function before declaring it.**
  - **이러한 이유로, 함수를 선언하기 전에 함수를 실행할 수 있다.**
- It is helpful when you want to abstract some logic into a function body and the actual implementation will be done at some later point of time.
  - 어떤 로직을 함수 body에 추상화하고, 실제 구현이 나중에 수행되기를 원할 때 유용하다.

```js
var num1 = 10;
var num2 = 20;

var result = add(num1, num2);	// 30 [선언 전에 실행]

function add(param1, param2) {
  return param1 + param2;
}
```

<br>

- Best practice: Always declare the function first and then execute it instead of relying on JavaScript Hoisting.
  - 가장 좋은 방법: JS 호이스팅에 의존하는 대신, 항상 함수를 먼저 선언한 후 실행한다.

<br>

#### Function Expression

###### 함수 표현식

<br>

- Any statement which assigns some value to some other variable is considered as an Expression.
  - 어떤 값을 다른 변수에 할당하는 명령문은 표현식(expression)으로 간주된다.

```js
var a = 100;
var b = 'Hello World';
```

<br>

- In case of Function Expression, a function is created without any name and then assigned to a variable.
  - 함수 표현식의 경우, 함수는 이름 없이 생성된 후 변수에 할당된다.

```js
var [name] = function(param1, param2, ...param3) {
  // 함수 Body & Logic
}

foo(1, 3, 4);
```

<br>

- **Limitation**: Function can't be executed until defined.
  - **제약**: 함수가 정의될 때까지 실행할 수 없다.

```js
var num1 = 10;
var num2 = 20;

var result = add(num1, num2);	// Uncaught TypeError: add is not a function

var add = function(param1, param2) {
  return param1 + param2;
}
```

<br>

- The below approach will work.
  - 아래 코드는 작동한다.

```js
var num1 = 10;
var num2 = 20;

var add = function(param1, param2) {
  return param1 + param2;
}

var result = add(num1, num2);	// 30
```

<br>

#### Named function expressions - Combination of Both Approaches

###### named 함수 표현식 (두 가지 방식의 결합)

<br>

- Now as you understand the differences between the function Declaration vs Expression, let's explore what happens when we mix both of them.
  - 함수 선언식과 함수 표현식의 차이를 이해했으니, 이 두 가지를 섞었을 때 어떻게 작동하는지 살펴보자.

```js
var num1 = 10;
var num2 = 20;

var addVariable = function addFunction(param1, param2) {
  return param1 + param2;
}
```

<br>

- Pay close attention to the fact that the function is `NOT` anonymous anymore and having a name as `addFunction`.
  - 함수가 더 이상 익명이 `아닌` 사실에 주의한다.
  - `addFunction`이라는 이름을 가진다.
- Also, it is assigned to a variable `addVariable`.
  - 또한, `addVariable` 변수에 할당된다.

<br>

- **Now just because you have appended a name to function keyword, that doesn't mean that it can be executed by that name.**
  - **function 키워드에 이름을 추가했지만, 해당 이름으로 실행될 수 있는 것은 아니다.**

```js
var result = addFunction(num1, num2);	// Uncaught ReferenceError: addFunction is not defined
```

<br>

- Rather, only the assigned variable name `addVariable` can be used to refer & execute it.
  - 할당된 변수 `addVariable`만 참조하고 실행할 수 있다.

```js
var result = addVariable(num1, num2);	// 30
```

<br>

#### Important points to consider:

###### 고려해야 할 중요 사항:

<br>

1. `addFunction` overshadows the `addVariable` in call stack of debugging tools.
   - 디버깅 도구의 call stack에서 `addFunction`은 `addVariable`을 덮어버린다.

<br>

###### Named 함수 표현식

![img](/assets/img/ravi-roshan-02.png)

<br>

###### 함수 표현식

![img](/assets/img/ravi-roshan-03.png)

<br>

2. In case of Named function expression, calling `addFunction() outside` throws error.
   - named 함수 표현식의 경우, `addFunction() 외부`에서 호출하면 에러가 발생한다.
   - `Uncaught ReferenceError: addFunction is not defined`

- But you can call it from inside the function and that will work.
  - 하지만 함수 내부에서 호출하면 작동한다.

```js
var num1 = 10;
var num2 = 20;

var addVariable = function addFunction(param1, param2) {
  var res = param1 + param2;
  
  if (res === 30) {
    res = addFunction(res, 10);
  }
  return res;
}

var result = addVariable(num1, num2);	// 40
```

<br>

- In this scenario, we are checking if res is 30.
  - 위 코드의 경우, res가 30인지 확인한다.
- If so, then calling the same function again by it's name `addFunction` with 30 & 10 as parameters which will return 40 as final output.
  - 30이 맞다면, 동일한 함수를 다시 호출한다.
  - 30과 10을 매개변수로 하는 `addFunction`에 의해, 최종 출력 40을 반환한다.

<br>

3. `One serious caveat` of using Named function expression in IE8 and below is that it mistakenly creates two completely separate function objects at two completely different times. ([Double take](http://blog.niftysnippets.org/2010/09/double-take.html))
   - IE8 이하에서 named 함수 표현식을 사용하는 것에 대한 `한 가지 심각한 경고`는, 완전히 다른 두 개의 함수 객체를 완전히 다른 시간에 생성한다는 것이다. ([Double take](http://blog.niftysnippets.org/2010/09/double-take.html))

- If you need to support IE8, it's probably best to stick with anonymous function expressions or function declarations, but avoid named function expressions.
  - IE8 지원이 필요한 경우, 익명 함수 표현식이나 함수 선언식을 사용하는 것이 가장 좋다.
  - named 함수 표현식은 사용하지 않는 것이 좋다.

<br>