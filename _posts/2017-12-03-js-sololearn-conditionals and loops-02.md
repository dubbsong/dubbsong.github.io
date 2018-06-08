---
layout: post
title: "SoloLearn 번역 - 02. The if else Statement (Conditionals and Loops)"
categories: javascript
tags: JS
---

## The else Statement (else 문)

- Use the **else** statement to specify a block of code that will execute if the condition is **false**.
  - **else** 문을 사용해서 조건이 **false**인 경우 실행할 코드 블록을 지정한다.

```js
if (expression) {
   // executed if condition is true
} else {
   // executed if condition is false
}
```

------

<br>

## The else Statement 02

- The example below demonstrates the use of an **if...else** statement.
  - 아래 예제는 **if...else** 문의 사용법을 보여준다.

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

- The above example says:
  - 위의 예제는 다음과 같다.

<br>

1. **if** *myNum1* is greater than *myNum2*, alert "This is my first condition".
   - *myNum1*이 *myNum2*보다 큰 경우 "This is my first condition"이라고 경고한다.
2. **else**, alert "This is my second condition".
   - 그렇지 않으면, "This is my second condition"이라고 경고한다.

<br>

- The browser will print out the second condition, as 7 is not greater than 10.
  - 7이 10보다 크지 않기 때문에, 브라우저는 두 번째 조건을 출력한다.

![SoloLearn img](/assets/img/sololearn-js-conditionals and loops-02-01.png)

------

<br>

## QUIZ

- The "else" statement is created to:
  - **Tell JavaScript to execute something if the condition is false**
  - Ignore the condition testing
  - Test a new condition for true or false

<br>

- Fill in the blanks to have a valid if...else statement:

```js
var age = 25;

if (age >= 18) {
   alert("Allowed.");
} else {
   alert("Not allowed.");
}
```

<br>