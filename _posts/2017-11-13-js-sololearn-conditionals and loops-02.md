---
layout: post
title: "02. if else 문 (Conditionals and Loops)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript if else Statement

###### JavaScript if else 문

------

<br>

<br>

## The else Statement

###### else 문

<br>

- Use the `else` statement to specify a block of code that will execute if the condition is `false`.
  - `else` 문을 사용해서 조건이 `false`일 경우 실행할 코드 블록을 지정한다.

```js
if (expression) {
   // executed if condition is true
} else {
   // executed if condition is false
}
```

<br>

<br>

- The example below demonstrates the use of an `if...else` statement.
  - 아래 예제는 `if...else` 문의 사용법을 보여준다.

```js
var myNum1 = 7;
var myNum2 = 10;
if (myNum1 > myNum2) {
   alert("This is my first condition");
} else {
   alert("This is my second condition");
}
```

<br>

- `if` *myNum1* is greater than *myNum2*, alert "This is my first condition".
  - `if` *myNum1*이 *myNum2*보다 크다면, "This is my first condition"을 alert 한다.
- `else`, alert "This is my second condition".
  - `else` 그렇지 않다면, "This is my second condition"을 alert 한다.

<br>

- The browser will print out the second condition, as 7 is not greater than 10.
  - 7이 10보다 크지 않기 때문에, 브라우저는 두 번째 조건을 출력한다.

![sololearn img](/assets/img/sololearn-js-conditionals and loops-02-01.png)

------

<br>

## QUIZ

- The "else" statement is created to:
  - "else" 문은 다음과 같이 생성된다.

> `Tell JavaScript to execute something if the condition is false`
>
> 조건이 false인 경우, JavaScript가 무언가를 실행하도록 지시한다

<br>

- Fill in the blanks to have a valid if...else statement:
  - if…else 문을 유효하게 작성해라.

```js
var age = 25;
if (age >= 18) {
   alert("Allowed.");
} else {
   alert("Not allowed.");
}
```

<br>