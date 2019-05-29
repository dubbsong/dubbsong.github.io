---
layout: post
title: "(ES6 02) 변수 & 문자열"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## var & let

- In ES6 we have three ways of declaring variables:
  - ES6에서는 변수를 선언하는 세 가지 방법이 있다.

```js
var a = 10;
const b = 'hello';
let c = true;
```

<br>

- The type of declaration used depends on the necessary `scope`.
  - 사용되는 선언 type은 필요한 `scope(범위)`에 따라 다르다.
- `Scope` is the fundamental concept in all programming languages that defines the visibility of a variable.
  - `scope(범위)`는 모든 프로그래밍 언어에서 변수의 가시성을 정의하는 기본 개념이다.

<br>

#### var & let

- Unlike the `var` keyword, which defines a variable globally, or locally to an entire function regardless of block scope, `let` allows you to declare variables that are limited in scope to the block, statement, or expression in which they are used.
  - 변수를 지역 또는 전역으로 전체 함수에 정의하는 `var` 키워드와는 달리, `let` 키워드는 scope가 block, 명령문, 표현식에 제한된 변수를 선언할 수 있다.

```js
if (true) {
   let name = 'Leo';
}

alert(name);	// Error
```

[코드 실행 확인](https://code.sololearn.com/1416/#js)

<br>

- In this case, the `name` variable is accessible only in the scope of the `if` statement because it was declared as `let`.
  - 위 코드에서 `name` 변수는 `let`으로 선언되었으므로, `if` 문 scope 내에서만 액세스할 수 있다.

<br>

- To demonstrate the difference in scope between `var` and `let`, consider this example:
  - `var`와 `let`의 scope 차이를 확인하기 위해 다음 예제를 살펴보자.

```js
function varTest() {
   var x = 1;
   
   if (true) {
      var x = 2;	// same variable
      console.log(x);	// 2
   }
   console.log(x);	// 2
}

function letTest() {
   let x = 1;
   
   if (true) {
      let x = 2;	// difference variable
      console.log(x);	// 2
   }
   console.log(x);	// 1
}

varTest();
letTest();
```

[코드 실행 확인](https://code.sololearn.com/1428/#js)

<br>

- One of the best uses for `let` is in loops:
  - `let`의 가장 좋은 사용 중 하나는 루프에서 사용할 때이다.

```js
for (let i = 0; i < 3; i++) {
   document.write(i);
}

// 012
```

[코드 실행 확인](https://code.sololearn.com/1417/#js)

<br>

- Here, the `i` variable is accessible only within the scope of the `for` loop, where it is needed.
  - 위 코드의 변수 `i`는 `for` 루프의 scope 내에서만 액세스할 수 있다.

<br>

> `let` is not subject to `Variable Hoisting`, which means that `let` declarations do not move to the top of the current execution context.
>
> `let`은 `Variable Hoisting(변수 호이스팅)`에 종속되지 않는다.
>
> 즉, `let` 선언은 현재 실행 컨텍스트의 맨 위로 이동하지 않는다.

------

<br>

## const

- `const` variables have the same scope as variables declared using `let`.
  - `const` 변수는 `let`을 사용해서 선언한 변수와 동일한 scope를 가진다.
- The difference is that const variables are `immutable` - they are not allowed to be reassigned.
  - const 변수는 `불변(변경할 수 없는)`이라는 차이점이 있다.
  - 다시 할당(재할당)을 할 수 없다.

```js
const a = 'Hello';
a = 'Bye';

// Uncaught TypeError: Assignment to constant variable.
```

[코드 실행 확인](https://code.sololearn.com/1418/#js)

<br>

> `const` is not subject to `Variable Hoisting` too, which means that `const` declarations do not move to the top of the current execution context.
>
> `const`도 `Variable Hoisting(변수 호이스팅)`에 종속되지 않는다.
>
> 즉, `const` 선언도 현재 실행 컨텍스트의 맨 위로 이동하지 않는다.

> Also note that ES6 code will run only in browsers that support it.
>
> 또한 ES6 코드를 지원하는 브라우저에서만 실행된다.

> Older devices and browsers that do not support ES6 will return a syntax error.
>
> ES6를 지원하지 않는 오래된 device나 브라우저에서는 syntax error를 반환한다.

------

<br>

## Template Literals in ES6

###### ES6의 템플릿 리터럴

<br>

- `Template literals` are a way to output variables in the string.
  - `템플릿 리터럴`은 문자열에서 변수를 출력하는 방법이다.
- Prior to ES6 we had to break the string.
  - ES6 이전에는 문자열을 끊어야 했다.

```js
let name = 'Leo';
let msg = 'Welcome ' + name + '!';

console.log(msg);	// Welcome Leo!
```

[코드 실행 확인](https://code.sololearn.com/1439/#js)

<br>

- ES6 introduces a new way of outputting variable values in strings.
  - ES6에서는 문자열에서 변수 값을 출력하는 새로운 방법을 도입했다.
- The same code above can be rewritten as:
  - 위와 동일한 코드를 다음과 같이 다시 작성할 수 있다.

```js
let name = 'Leo';
let msg = `Welcome ${name}!`;

console.log(msg);	// Welcome Leo!
```

[코드 실행 확인](https://code.sololearn.com/1440/#js)

<br>

- Notice, that template literals are enclosed by the `backtick` (\`) character instead of double or single quotes.
  - 템플릿 리터럴은 큰따옴표나 작은따옴표 대신, `백틱` (\`) 문자로 묶는다.
- The `${expression}` is a placeholder, and can include any expression, which will get evaluated and inserted into the template literal.
  - `${expression}`은 placeholder(자리 표시자)이며, 모든 표현식을 포함할 수 있다.

```js
let a = 8;
let b = 34;
let msg = `The sum is ${a + b}`;

console.log(msg);	// 42
```

[코드 실행 확인](https://code.sololearn.com/1441/#js)

<br>

> To escape a backtick in a template literal, put a backslash \\ before the backtick.
>
> 템플릿 리터럴에서 백틱을 이스케이프하려면, 백틱 앞에 백슬래시 \\를 놓으면 된다.

------

<br>

## QUIZ

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```js
function letItBe() {
   let v = 2;
   
   if (true) {
      let v = 4;
      console.log(v);
   }
   console.log(v);
}

letItBe();
```

> `42`

<br>

- Fill in the blanks to make a constant named total and the variable i that is only accessible inside the loop.
  - 루프 내에서만 액세스할 수 있는 변수 i와, total이라는 const를 작성해라.

```js
const total = 100;
let sum = 0;

for (let i = 0; i < total; i++) {
   sum += i;
}
```

<br>

- Fill in the blanks to output "We are learning ES6!".
  - "We are learning ES6!"를 출력해라.

```js
let n = 6;
let s = 'ES';
let msg = `We are learning ${s + n}!`;

console.log(msg);	// We are learning ES6!
```

<br>