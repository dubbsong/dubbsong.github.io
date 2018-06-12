---
layout: post
title: "SoloLearn 번역 - 04. The switch Statement (Conditionals and Loops)"
categories: javascript
tags: JS
---

## Switch (switch 문)

- In cases when you need to test for multiple conditions, writing**if else** statements for each condition might not be the best solution.
  - 여러 조건을 테스트해야 하는 경우, 각 조건에 대한 **if else** 문이 최상의 해결 방법이 아닐 수도 있다.
- The **switch statement** is used to perform different actions based on different conditions.
  - **switch 문**은 다른 조건에 따라 다른 동작을 수행하는 데 사용된다.

<br>

- Syntax:

```js
switch (expression) {
   case n1:
      statements
      break;
   case n2:
      statements
      break;
   default:
      statements
}
```

<br>

- The switch expression is evaluated once.
  - switch 표현식은 한 번 평가된다.
- The value of the expression is compared with the values of each **case**.
  - 표현식의 값은 각 **case**의 값과 비교된다.
- If there is a match, the associated block of code is executed.
  - 일치하는 것이 있으면, 연관된 코드 블록이 실행된다.

<br>

> You can achieve the same result with multiple if...else statements, but the switch statement is more effective in such situations.
>
> if...else 문을 여러 개 사용해서 동일한 결과를 얻을 수 있지만, switch 문은 이러한 상황에서 더 효과적이다.

------

<br>

## The switch Statement (switch 문)

- Consider the following example.
  - 다음 예제를 고려해보자.

```js
var day = 2;

switch (day) {
   case 1:
      document.write("Monday");
      break;
   case 2:
      document.write("Tuesday");
      break;
   case 3:
      document.write("Wednesday");
      break;
   default:
      document.write("Another day");
}


// Outputs "Tuesday"
```

<br>

> You can have as many **case** statements as needed.
>
> 필요한 만큼 **case** 문을 가질 수 있다.

------

<br>

## The break Keyword (break 키워드)

- When JavaScript code reaches a **break** keyword, it breaks out of the switch block.
  - JavaScript 코드가 **break** 키워드에 도달하면, switch 블록에서 빠져나온다.
- This will stop the execution of more code and case testing inside the block.
  - 이것은 블록 내부에서 더 많은 코드 및 case 테스팅을 멈추게 된다.

<br>

> Usually, a **break** should be put in each case statement.
>
> 일반적으로, 각 case 문에 **break**를 넣어야 한다.

------

<br>

## The default Keyword (default 키워드)

- The **default** keyword specifies the code to run if there is no case match.
  - **default** 키워드는 case가 일치하지 않을 경우 실행할 코드를 지정한다.

```js
var color = "yellow";

switch (color) {
   case "blue":
      document.write("This is blue.");
      break;
   case "red":
      document.write("This is red.");
      break;
   case "green":
      document.write("This is green.");
      break;
   case "orange":
      document.write("This is orange.");
      break;
   default:
      document.write("Color not found.");
}


// Outputs "Color not found."
```

<br>

> The default block can be omitted, if there is no need to handle the case when no match is found.
>
> 일치하는 것이 없어서 case 문을 처리할 필요가 없다면, default 블록을 생략할 수 있다.

------

<br>

## QUIZ

- The switch statement can be used to replace ...
  - **multiple if else statements**
  - variable declarations
  - comments

<br>

- How many "case" statements are usually used in the "switch" statement?
  - 2 - for "true" and "false"
  - Only 5
  - **One for each possible answer**

<br>

- What is the output of this code?

```js
var x = 3;

switch (x) {
   case 1:
      document.write(x);
      break;
   case 2:
      document.write(x + 2);
      break;
   default:
      document.write(x + 5);
}


// 8
```

<br>

- The "default" statement is used ...
  - To finish the "case" statement
  - **When no match is found** (일치하는 항목이 없는 경우)
  - Because it is obligatory

<br>