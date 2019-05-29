---
layout: post
title: "(ES6 03) 루프 & 함수"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## Loops in ECMAScript 6

###### ES6의 루프

<br>

- In JavaScript we commonly use the `for` loop to iterate over values in a list:
  - JavaScript에서는 일반적으로 `for` 루프를 사용해서 list의 값을 반복한다.

```js
let arr = [1, 2, 3];

for (let i = 0; i < arr.length; i++) {
   console.log(arr[i]);
}

// 1
// 2
// 3
```

[코드 실행 확인](https://code.sololearn.com/1429/#js)

<br>

- The `for…in` loop is intended for iterating over the enumerable keys of an object.
  - `for…in` 루프는 객체의 셀 수 있는 key를 반복하는 데 사용된다.

```js
let obj = {a: 1, b: 2, c: 3};

for (let i in obj) {
   console.log(i);
}

// a
// b
// c
```

[코드 실행 확인](https://code.sololearn.com/1430/#js)

<br>

> The `for…in` loop should `NOT` be used to iterate over arrays because, depending on the JavaScript engine, it could iterate in an arbitrary order.
>
> `for…in` 루프는 JavaScript 엔진에 따라 임의의 순서로 반복할 수 있으므로, 배열을 반복하는 데 사용해서는 안 된다.

> Also, the iterating variable is a `string`, not a number, so if you try to do any math with the variable, you'll be performing string concatenation instead of addition.
>
> 또한 iterating 변수는 숫자가 아닌 `문자열`이므로, 이 변수를 사용해서 계산을 수행하려고 하면 문자열 연결을 수행하게 된다.

<br>

- ES6 introduces the new `for…of` loop, which creates a loop iterating over iterable objects.
  - ES6에서는 `for...of` 루프를 도입했다.
  - 이는 반복 가능한 객체를 반복하는 루프를 생성한다.

```js
let list = ['x', 'y', 'z'];

for (let i of list) {
   console.log(i);
}

// x
// y
// z
```

[코드 실행 확인](https://code.sololearn.com/1177/#js)

<br>

- During each iteration the `i` variable is assigned the corresponding element in the list.
  - 매 반복마다 `i` 변수는 list의 해당 element를 할당한다.

<br>

- The `for…of` loop works for other iterable objects as well, including `strings`:
  - `for…of` 루프는 `문자열`을 포함한, 다른 반복 가능한 객체에서도 동작한다.

```js
for (let i of 'Hello') {
   console.log(i);
}

// H
// e
// l
// l
// o
```

[코드 실행 확인](https://code.sololearn.com/1166/#js)

<br>

> The `for…of` loop also works on the newly introduced collections (`Map`, `Set`, `WeakMap`, and `WeakSet`).
>
> `for…of` 루프는 새로 도입된 collection((`Map`, `Set`, `WeakMap`, `WeakSet`)에서도 동작한다.

> Note that ES6 code will run only in browsers that support it.
>
> ES6 코드를 지원하는 브라우저에서만 실행된다.

> Older devices and browsers that do not support ES6 will return a syntax error.
>
> ES6를 지원하지 않는 오래된 device나 브라우저에서는 syntax error를 반환한다.

------

<br>

## Functions in ECMAScript 6

###### ES6의 함수

<br>

- Prior to ES6, a JavaScript function was defined like this:
  - ES6 이전의 JavaScript 함수는 다음과 같이 정의되었다.

```js
function add(x, y) {
   var sum = x + y;
   console.log (sum);
}

add(1, 2);	// 3
```

[코드 실행 확인](https://code.sololearn.com/1434/#js)

<br>

- ES6 introduces a new syntax for writing functions.
  - ES6에서는 함수 작성을 위한 새로운 구문을 도입했다.
- The same function from above can be written as:
  - 위 코드와 동일한 함수를 다음과 같이 작성할 수 있다.

```js
const add = (x, y) => {
   let sum = x + y;
   console.log(sum);
}

add(1, 2);	// 3
```

[코드 실행 확인](https://code.sololearn.com/1182/#js)

<br>

- This new syntax is quite handy when you just need a simple function with one argument.
  - 이 새로운 구문은 하나의 인수로 간단한 함수를 작성할 때 꽤 편리하다.
- You can skip typing `function` and `return`, as well as some parentheses and braces.
  - 괄호와 중괄호뿐만 아니라, `function`과 `return` 타이핑을 생략할 수 있다.

```js
const greet = x => 'Welcome ' + x;

alert(greet('Leo'));	// Alert 'Welcome Leo'
```

[코드 실행 확인](https://code.sololearn.com/1183/#js)

<br>

- The code above defines a function named `greet` that has one argument and returns a message.
  - 위 코드는 `greet`라는 함수를 정의한다.
  - 이 함수는 인수를 하나 가지고, 메시지를 반환한다.

<br>

- If there are no parameters, an empty pair of parentheses should be used.
  - 만약 매개변수가 없다면, 빈 괄호 쌍을 사용해야 한다.

```js
const x = () => alert('Hi');

x();	// Alert 'Hi'
```

[코드 실행 확인](https://code.sololearn.com/1437/#js)

<br>

- The syntax is very useful for inline functions.
  - 이 구문은 inline 함수에 매우 유용하다.
- For example, let's say we have an array, and for each element of the array we need to execute a function.
  - 예를 들어, 배열이 있다고 가정해보자.
  - 이 배열의 각 element에 대해 함수를 실행해야 한다.
- We use the `forEach` method of the array to call a function for each element:
  - 각 element에 대한 함수를 호출하기 위해, 배열의 `forEach` 메소드를 사용한다.

```js
var arr = [2, 3, 7, 8];

arr.forEach(function(i) {
   console.log(i * 2);
});

// 4
// 6
// 14
// 16
```

[코드 실행 확인](https://code.sololearn.com/1435/#js)

<br>

- However, in ES6, the code above can be rewritten as following:
  - 하지만 ES6에서는, 위 코드를 다음과 같이 다시 작성할 수 있다.

```js
const arr = [2, 3, 7, 8];

arr.forEach(i => {
   console.log(i * 2);
});
```

[코드 실행 확인](https://code.sololearn.com/1436/#js)

<br>

> The code is shorter and looks pretty nice, doesn't it?
>
> 코드가 짧아서 더 보기 좋지 않은가?

------

<br>

## Default Parameters in ES6

###### ES6의 default 매개변수

<br>

- In ES6, we can put the default values right in the signature of the functions.
  - ES6에서는 함수의 signature에 기본 값을 바로 넣을 수 있다.

```js
/*
function test(a, b = 3, c = 42) {
   return a + b + c;
}
*/

const test = (a, b = 3, c = 42) => a + b + c;

console.log(test(5));	// 50
```

[코드 실행 확인](https://code.sololearn.com/1438/#js)

<br>

- And here's an example of an arrow function with default parameters:
  - 다음은 default 매개변수가 있는 화살표 함수의 예제이다.

```js
const test = (a, b = 3, c = 42) => {
   return a + b + c;
}

console.log(test(5));	// 50
```

<br>

> Default value expressions are evaluated at function call time from left to right.
>
> default 표현식은 함수 호출 시 왼쪽에서 오른쪽으로 평가된다.

> This also means that default expressions can use the values of previously-filled parameters.
>
> 이는 default 표현식이 이전에 채워진 매개변수의 값을 사용할 수 있음을 의미한다.

------

<br>

## QUIZ

- Fill in the blanks to iterate through all the characters using the for…of loop.
  - for…of 루프를 사용해서 모든 문자를 반복해라.

```js
for (let i of 'SoloLearn') {
   console.log(i);
}
```

<br>

- Fill in the blanks to declare an arrow function that takes an array and prints the odd elements.
  - 홀수를 출력하는 화살표 함수를 선언해라.

```js
const printOdds = (arr) => {
   arr.forEach(i => {
      if (i % 2 != 0) console.log(i);
   });
}
```

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```js
function magic(a, b = 40) {
   return a + b;
}

console.log(magic(2));
```

> `42`

<br>