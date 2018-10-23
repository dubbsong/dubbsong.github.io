---
layout: post
title: "(Functions 01) 사용자 정의 함수"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

# JavaScript User-Defined Functions

###### 사용자 정의 함수

------

<br>

<br>

## JavaScript Functions

###### JavaScript 함수

<br>

- A JavaScript `function` is a block of code designed to perform a particular task.
  - JavaScript `함수`는 특정 작업을 수행하도록 설계된 코드 블록이다.

<br>

#### The main advantages of using functions:

###### 함수 사용의 주요 이점:

<br>

- Code `reuse`: Define the code once, and use it many times.
  - 코드 `재사용`: 코드를 한 번 정의하고, 여러 번 사용한다.

<br>

- Use the same code many times with different `arguments`, to produce different results.
  - 서로 다른 `인수`를 사용해서 동일한 코드를 여러 번 사용하면, 다른 결과가 생성된다.

<br>

> A JavaScript function is executed when "something" invokes, or calls, it.
>
> JavaScript 함수는 "무언가"를 invoke(호출)하거나 call(호출)할 때 실행된다.

------

<br>

## Defining a Function

###### 함수 정의

<br>

- To define a JavaScript function, use the `function` keyword, followed by a `name`, followed by a set of `parentheses()`.
  - JavaScript 함수를 정의하려면, `function` 키워드를 사용하고, `name` 뒤에 `괄호()`를 배치한다.

<br>

- The code to be executed by the function is placed inside curly brackets {}.
  - 함수에 의해 실행될 코드는 중괄호{} 내에 놓인다.

```js
function name() {
   // 실행될 코드
}
```

<br>

> Function names can contain letters, digits, underscores, and dollar signs (same rules as variables).
>
> 함수 name에는 문자, 숫자, 밑줄, 달러 기호(변수와 동일한 규칙)가 포함될 수 있다.

------

<br>

## Calling a Function

###### 함수 호출

<br>

- To execute the function, you need to call it.
  - 함수를 실행하기 위해서는 함수를 호출해야 한다.
- To call a function, start with the name of the function, then follow it with the arguments in parentheses.
  - 함수를 호출하기 위해 함수의 이름으로 시작한 다음, 인수를 괄호 안에 넣어라.

<br>

- Example:

```js
function myFunction() {
   alert("Calling a Function!");
}

myFunction();	// alert "Calling a Function!"
```

[코드 실행 확인](https://code.sololearn.com/675/#js)

<br>

> Always remember to end the statement with a `semicolon` after calling the function.
>
> 함수를 호출한 후에는 항상 `세미콜론`으로 표현문을 끝낸다.

<br>

<br>

- Once the function is defined, JavaScript allows you to call it as many times as you want to.
  - JavaScript는 함수가 한 번 정의되면, 원하는 만큼 여러 번 함수를 호출할 수 있다.

```js
function myFunction() {
   alert("Alert box!");
}

myFunction();	// "Alert box!"

// some other code

myFunction();	// "Alert box!"
```

[코드 실행 확인](https://code.sololearn.com/676/#js)

<br>

> You can also call a function using this syntax: myFunction().call().
>
> myFunction().call()과 같은 구문을 사용해서 함수를 호출할 수도 있다.

> The difference is that when calling in this way, you're passing the 'this' keyword to a function.
>
> 이런 방식으로 호출할 때의 차이점은, 'this' 키워드를 함수에 전달한다는 것이다.

------

<br>

## QUIZ

- What is a function?
  - 함수란 무엇인가?

> `A certain block of code that can be reused over and over again`
>
> 반복적으로 재사용 할 수 있는 특정 코드 블록

<br>

- Add the corresponding keyword and symbols to create a function named "test".
  - 해당 키워드와 기호를 추가해서 "test"라는 함수를 작성해라.

```js
function test() {
   /* some code */
}
```

<br>

- Fill in the blanks to define and call the "hello" function.
  - "hello" 함수를 정의하고 호출해라.

```js
function hello() {
   alert("Hi there");
}

hello();
```

<br>

- How many times can the function be executed inside a webpage?
  - 웹페이지에서 몇 번이나 함수를 실행할 수 있는가?

> `As many as needed`
>
> 필요한 만큼, 원하는 만큼

<br>
