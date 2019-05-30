---
layout: post
title: "(번역) JS 표현식에 대해 알아야 할 모든 것"
categories: js
---

###### [Promise Tochi](https://dev.to/promhize/javascript-in-depth-all-you-need-to-know-about-expressions-statements-and-expression-statements-5k2) 포스팅 번역

<br>

## All you need to know about JavaScript's Expressions

###### JS 표현식에 대해 알아야 할 모든 것

<br>

- By the end of this article, you should be able to describe in detail how the code in the image below works and why it works.
  - 이 글의 끝에서는, 아래 코드의 작동 방식과 작동 원리에 대해 상세하게 설명할 수 있어야 한다.

```js
{} + 1	// 1
{2} + 2	// 2
{2 + 2} + 3	// 3
{2 + 2} - 3	// -3
```

<br>

- There are two major syntactic categories in JavaScript:
  - JS에는 크게 두 가지 구문 종류가 있다.

<br>

1. Statements
   - 명령문
2. Expressions
   - 표현문

<br>

- It is important to make this distinction because expressions can act like statements, which is why we also have Expression statements.
  - 표현식이 명령문처럼 동작할 수 있으므로, 이러한 구분을 하는 것이 중요하다.
  - 그래서 표현식 명령문(Expression statement)도 살펴볼 것이다.
- Though, on other the hand, statements cannot act like expressions.
  - 반면에, 명령문이 표현식처럼 동작할 수는 없다.

<br>

### EXPRESSIONS

###### 표현식

<br>

### Expressions produce a value

###### 표현식은 값을 생성한다

<br>

- Expressions are JavaScript code snippets that result in a single value.
  - 표현식은, 하나의 값이 되는 JS 코드 조각이다.
- Expressions can be as long as you want them to be, but they would always result in a single value.
  - 표현식은 원하는 만큼 길어질 수 있지만, 항상 하나의 값이 된다.

```js
2 + 2 * 3 / 2

(Math.random() * (100 - 20)) + 20

functionCall()

window.history ? useHistory() : noHistoryFallback()

1+1, 2+2, 3+3

declaredVariable

true && functionCall()

true && declaredVariable
```

<br>

- All of the above are expressions, and can appear anywhere JavaScript expects a value.
  - 위 코드는 모두 표현식이다.
  - JS가 값을 기대하는 곳이면 어디든 언급할 수 있다.

- So that the argument to `console.log` below, resolves to a single value, that is logged to the console.
  - 아래 `console.log`의 인수는 console에 로깅될 때 하나의 값으로 변환된다.

```js
console.log(true && 2 * 9)	// 18
```

<br>

#### Expressions don't necessarily change a state

######표현식이 꼭 state를 변경하지는 않는다

<br>

- For example:

```js
const assignedVariable = 2;	// 이는 명령문이고, assignedVariable은 state다.

assignedVariable + 4	// 표현식

assignedVariable * 10	// 표현식

assignedVariable - 10	// 표현식

console.log(assignedVariable)	// 2
```

<br>

- Despite all the expression in the snippet above, assignedVariable's value is still 2.
  - 모든 표현식에도 불구하고, assignedVariable의 값은 여전히 2이다.
- So why the `necessarily` in the heading for this section, it's because function calls are expressions but a function can contain statements that change state.
  - 그렇다면 왜 이 섹션의 제목에 `necessarily`가 있는가?
  - 함수 호출은 표현식이지만, 함수는 state를 변경하는 명령문을 포함할 수 있다.

<br>

- So `foo()` in itself is an expression, that either returns undefined or some other value, but if `foo` was written as then, even though its call is an expression, its call has also resulted in a state change.
  - 따라서 foo 내의 `foo()`는 표현식이다.
  - 이는 undefined 또는 다른 값을 반환한다.
  - 하지만 `foo`가 다음과 같이 작성되었다면, 그 호출이 표현식이라 해도 호출은 state를 변경하는 결과를 낳는다.

```js
const foo = foo() => {
  assignedVariable = 14
}
```

<br>

- So a better way to rewrite the foo function and statement would be:
  - foo 함수와 명령문을 다시 작성하는 더 좋은 방법은 다음과 같다.

```js
const foo = foo() => {
  return 14	// 가독성을 위한 명시적 반환
}

assignedVariable = foo()
```

<br>

- Or even better:
  - 다른 더 좋은 방법은 다음과 같다.

```js
const foo = foo(n) => {
  return n	// 가독성을 위한 명시적 반환
}

assignedVariable = foo(14)
```

<br>

- This way your code is more readable, composable, and there is a clear distinction and separation between expression and statements.
  - 이렇게 하면 코드의 가독성이 좋아지고, 안정적이며, 표현식과 명령문을 명확히 구분할 수 있다.
- This a fundamental of functional and declarative JavaScript.
  - 이것이 선언적 및 함수형 JS의 핵심이다.

<br>

### Statements

###### 명령문

<br>

- Statements are the headache of functional programming.
  - 명령문은 함수형 프로그래밍의 골칫거리이다.
- Basically, statements perform actions, they do things.
  - 기본적으로 명령문은 동작을 수행한다.

<br>

- In JavaScript, statements can never be used where a value is expected.
  - JS에서 명령문은 값을 기대하는 곳에 사용될 수 없다.
- So they cannot be used as function arguments, right-hand side of assignments, operators operand.
  - 따라서 함수의 인수, 할당의 오른쪽, 연산자의 피연산자(연산의 대상이 되는 데이터)로 사용될 수 없다.

```js
foo(if () { return 2 })	// JS engine mind = blown
```

<br>

- These are all JavaScript statements:
  - 다음은 모두 JS 명령문이다.

<br>

1. if
2. if-else
3. while
4. do-while
5. for
6. switch
7. for-in
8. with (deprecated)
9. debugger
10. variable declaration

<br>

- If you type the snippet below in your browser's console and hit enter, you will see that it returns `18` but despite that you cannot use it as an expression or where JavaScript expects a value.
  - 브라우저의 console에 아래 코드를 입력하고 enter를 누르면 `18`을 반환하지만, 표현식이나 JS가 값을 기대하는 곳에 사용할 수 없다.

```js
if (true) {9+9}
```

<br>

- It is weird because you'd expect statements not to return anything, since the return value is pretty much useless if you cannot use it.
  - 이는 이상하다.
  - 명령문이 아무것도 반환하지 않을 것이라고 예상하기 때문이다.
  - 그러므로 명령문을 사용할 수 없다면, 반환 값은 거의 쓸모가 없다.
- That's JavaScript for you, weird.
  - 이것이 JS이다. 이상하다.

<br>

### Function declarations, Function expressions and Named Function expressions

###### 함수 선언식, 함수 표현식, named 함수 표현식

<br>

- A function declaration is a statement.
  - 함수 선언식은 명령문이다.

```js
function foo(func) {
  return func.name
}
```

<br>

- A function expression is an expression, what you call an anonymous function.
  - 함수 표현식은 표현식이고, 익명 함수라고 한다.

```js
console.log(foo(function() {}))	// ''
```

<br>

- A named function expression is an expression, like an anonymous function, but it has a name.
  - named 함수 표현식은 익명 함수처럼 표현식이지만, 이름을 가진다.

```js
console.log(foo(function myName() {}))	// 'myName'
```

<br>

- The distinction between function as an expression and function as a declaration boils down to understanding this:
  - 표현식으로의 함수와 선언식으로의 함수 사이의 구분은, 다음을 이해하는 것으로 볼 수 있다.
- **Whenever you declare a function where JavaScript is expecting a value, it will attempt to treat it as a value, if it can't use it as a value, an error will be thrown.**
  - JS가 값을 기대하는 곳에 함수를 선언할 때마다, 이를 값으로 처리하려고 시도할 것이다.
  - 값으로 사용할 수 없다면, 에러가 발생한다.
- **Whereas declaring a function at the global level of a script, module, or top level of a block statement (that is, where it is not expecting a value), will result in a function declaration.**
  - 하지만 global level의 스크립트, 모듈, top level의 블록 명령문(값을 기대하는 곳이 아닌)에서 함수를 선언한다면, 함수 선언식이 된다.

<br>

- For example:

```js
if () {function foo() {}}	// top level 블록, 선언식

function foo() {}	// global level, 선언식

function foo() {function bar() {}}	// top level 블록, 선언식

function foo() {
  return function bar () {}	// named 함수 표현식
}

foo(function () {})	// 익명 함수 표현식

functino foo() {
  return function bar() {
    function baz() {}	// top level 블록, 선언식
  }
}

function() {}	// SyntaxError: function statement requires a name

if (true) {
  function() {}	// SyntaxError: function statement requires a name
}
```

<br>

### Converting Expression to Statements: Expression Statements

###### 표현식을 명령문으로 변환하기: 표현식 명령문

<br>

- You can convert expressions to expression statement, just by adding a semi-colon to the end of the line or allowing automatic semi-colon insertion to do the work.
  - 표현식(expression)을 표현식 명령문(expression statement)으로 변환할 수 있다.
  - 단지 줄 끝에 세미콜론을 추가하면 된다.

```js
2+2;	// 표현식 명령문
foo();	// 표현식 명령문
```

<br>

- `2+2` itself is an expression but the complete line is a statement.
  - `2+2` 자체는 표현식이지만, 줄 전체는 명령문이다.

```js
2+2	// on its own is an opposition

foo(2+2)	// 값을 기대하는 곳이면 어디든 사용할 수 있다.

true ? 2+2 : 1+1

function foo() { return 2+2 }

2+2;	// 표현식 명령문
foo(2+2;)	// SyntaxError
```

<br>

### Semi-colon vs Comma operator

###### 세미콜론 vs 쉼표 연산자

<br>

- With semi-colon, you can keep multiple statements on the same line.
  - 세미콜론을 사용하면, 여러 명령문을 동일한 줄에 놓을 수 있다.

```js
const a; function foo() {}; const b = 2
```

<br>

- The comma operator allows you to chain multiple expression, returning only the last expression.
  - 쉼표 연산자를 사용하면, 여러 표현식을 연결해서 마지막 표현식만 반환할 수 있다.

```js
console.log((1+2, 3, 4))	// 4

console.log((2, 9/3, function() {}))	// function() {}

console.log((3, true ? 2+2 : 1+1))	// 4
```

<br>

- Sidenote: one way to tell the JavaScript engine to expect a value is via parentheses, (), without the parentheses, each expression will be treated as an argument to console.log.
  - 참고: JS 엔진에 값을 기대하도록 알려주는 한 가지 방법은, 괄호를 사용하는 것이다.
  - 괄호가 없으면, 각 표현식은 console.log에 대한 인수로 간주된다.

<br>

```js
function foo() { return 1, 2, 3, 4 }
foo()	// 4
```

- All the expressions will be evaluated from left to right, and the last one will be returned.
  - 모든 표현식은 왼쪽에서 오른쪽으로 계산되고, 마지막 값이 반환된다.

<br>

### IIFEs (Immediately Invoked Function Expressions)

###### 즉시 호출되는 함수 표현식

<br>

- An anonymous function can be an expression, if we use it where JavaScript is expecting a value, that means we if we can tell JavaScript to expect a value with parentheses, we can pass an anonymous function as that value.
  - 익명함수는 표현식으로 사용될 수 있다.
  - JS가 값을 기대하는 곳에, 즉 괄호가 있는 값을 기대하도록 JS에 알려줄 수 있는 경우, 익명 함수를 값으로 전달할 수 있다.

```js
function () {}
```

<br>

- So while the snippet above is invalid, the snippet below is valid.
  - 위 코드는 유효하지 않지만, 아래 코드는 유효하다.

```js
(function () {})	// function () {}을 반환한다.
```

<br>

- If putting a anonymous function inside a parentheses immediately returns the same anonymous function, that means we can call it straight away, like this:
  - 익명 함수를 괄호 내에 놓으면 즉시 동일한 익명 함수를 반환한다.
  - 즉, 곧바로 호출할 수 있다.

```js
(function () {
  // do something
})()
```

<br>

- So, these are possible.
  - 따라서, 다음과 같은 것도 가능하다.

```js
(function () {
  console.log("immediately invoke anonymous function call")
})()	// "immediately invoke anonymous function call"

(function () {
  return 3
})()	// 3

console.log((function () {
  return 3
})())	// 3

// 인수를 전달할 수도 있다.
(function (a) {
  return a
})("I'm an argument")	// I'm an argument
```

<br>

### Object literals vs Block Statements

###### 객체 리터럴 vs 블록 명령문

<br>

- Sidenote: this is valid JavaScript.
  - 참고: 아래 코드는 유효한 JS이다.

```js
r: 2+2	// 유효하다.

foo()

const foo = () => {}
```

<br>

- The above are sequence of statements in the global scope that will be parsed as valid JavaScript and executed.
  - 위 코드는 전역 범위 내 일련의 명령문이다.
  - 유효한 JS로 구문 분석되어 실행된다.
- The `r` is what you'll call a label, and they are mostly useful in breaking loops.
  - `r`은 label이라고 부르며, 주로 반복을 중단하는 데 유용하다.

- For example:

```js
loop: {
  for (const i = 0; i < 2; i++) {
    for (const n = 0; n < 2; n++) {
      break loop	// 바깥 반복을 중단시켜서, 전체 반복을 중단한다.
    }
  }
}
```

<br>

- You can prepend a label to any expression or expression statement, note that you not are creating a variable lab by doing this:
  - 모든 표현식이나 표현식 명령문 앞에 label을 추가할 수 있다.
  - 다음 코드를 보고, 변수 lab을 생성하지 않는다는 것에 주의한다.

```js
lab: function a () {}
console.log(lab)	// ReferenceError: lab is not defined
```

<br>

- Curly braces, {}, allow you to group expression statements and statements.
  - 중괄호를 사용하면, 표현식 명령문과 명령문을 묶을 수 있다.

```js
{var a = "b"; func(); 2+2}	// 4
```

<br>

- If you paste the above in your browsers console, it will return 4 and when you do `console.log(a)`, you will get string `b`.
  - 위 코드를 브라우저 console에 붙여 넣으면, 4를 반환한다.
  - `console.log(a)`를 입력하면, 문자열 `b`를 반환한다.
- You can call that a block statement, which is different from the object literal you might be used to.
  - 이를 블록 명령문이라고 한다.
  - 익숙한 객체 리터럴과는 다르다.

```js
console.log({a: 'b'})	// {a: 'b'}

console.log({var a = "b", func(), 2+2})	// SyntaxError

const obj = {var a = "b", func(), 2+2}	// SyntaxError
```

<br>

- You cannot use a block statement as a value or expression, because console.log is a function, it cannot accept a statement as an argument.
  - console.log는 함수이므로, 블록 명령문을 값이나 표현식으로 사용할 수 없다.
  - 명령문을 인수로 사용할 수 없다.
- It can accept an object literal though.
  - 하지만 객체 리터럴은 인수로 사용할 수 있다.
- I hope you understood all I explained above, cause the next snippet below might throw you off.
  - 위에서 설명한 모든 것을 이해했길 바란다.

```js
{} + 1	// 1

{2} + 2	// 2

{2+2} + 3	// 3

{2+2} - 3	// -3
```

<br>

- You might expect it to throw either a syntax error or to return 1, 4, 7 respectively.
  - 아마 구문 에러가 발생하거나, 각각 1, 4, 7을 반환할 것으로 생각했을 수 있다.
- Remember statements aren't supposed to return anything because they can't be used as values.
  - 명령문은 값으로 사용될 수 없으므로, 아무것도 반환할 수 없다.
- So JavaScript rather throwing an error, attempts to convert the operands of the `+` operator to a number or string, if it can't then it throws.
  - 따라서 JS는 에러 대신, `+` 연산자의 피연산자를 숫자나 문자열로 변환한다.
  - 변환할 수 없다면, 에러를 반환한다.
- So whatever is returned by the block statement, is implicitly coerced to `0` used as the operand.
  - 따라서 블록 명령문에 의해 반환되는 것은, 암시적으로 `0`으로 강제 변환되어 피연산자로 사용된다.

<br>