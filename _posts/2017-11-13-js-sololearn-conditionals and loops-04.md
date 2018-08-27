---
layout: post
title: "04. switch 문 (Conditionals and Loops)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript switch Statement

###### JavaScript switch 문

<br>

- In cases when you need to test for multiple conditions, writing `if else` statements for each condition might not be the best solution.
  - 여러 조건을 테스트해야 하는 경우, 각 조건에 대한 `if else` 문 작성이 최선의 해결이 아닐 수도 있다.
- The `switch statement` is used to perform different actions based on different conditions.
  - `switch 문`은 다른 조건에 따라 다른 동작을 수행하는 데 사용된다.

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
- The value of the expression is compared with the values of each `case`.
  - 표현식의 값은 각 `case`의 값과 비교된다.
- If there is a match, the associated block of code is executed.
  - 일치하는 것이 있으면, 연관된 코드 블록이 실행된다.

<br>

> You can achieve the same result with multiple if...else statements, but the switch statement is more effective in such situations.
>
> 여러 if...else 문을 사용해서 동일한 결과를 얻을 수 있지만, switch 문은 이러한 상황에서 더 효과적이다.

<br>

<br>

- Consider the following example.
  - 다음 예제를 살펴보자.

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

// Outputs "Tuesday
```

[코드 실행 확인 링크](https://code.sololearn.com/665/#js)

<br>

> You can have as many `case` statements as needed.
>
> 필요한 만큼 여러 `case` 문을 사용할 수 있다.

------

<br>

## The break Keyword

###### break 키워드

<br>

- When JavaScript code reaches a `break` keyword, it breaks out of the switch block.
  - JavaScript 코드가 `break` 키워드에 도달하면, switch 블록에서 빠져나온다.
- This will stop the execution of more code and case testing inside the block.
  - 이렇게 되면, 블록 내의 코드 실행과 case 테스트가 중지된다.

<br>

> Usually, a `break` should be put in each case statement.
>
> 일반적으로, 각 case 문에 `break`가 있어야 한다.

------

<br>

## The default Keyword

###### default 키워드

<br>

- The `default` keyword specifies the code to run if there is no case match.
  - `default` 키워드는 일치하는 case가 없는 경우 실행할 코드를 지정한다.

```js
var color = "yellow";
switch(color) {
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

[코드 실행 확인 링크](https://code.sololearn.com/666/#js)

<br>

> The default block can be omitted, if there is no need to handle the case when no match is found.
>
> 일치하는 것이 없을 때 case를 처리가 필요가 없는 경우, default 블록을 생략할 수 있다.

------

<br>

## QUIZ

- The switch statement can be used to replace...
  - switch 문을 사용해서 …을 대체할 수 있다.

> `multiple if else statements`
>
> 여러 if else 문

<br>

- How many "case" statements are usually used in the "switch" statement?
  - 얼마나 많은 "case" 문이 "switch" 문에서 보통 사용되는가?

> `One for each possible answer`
>
> 각 가능한 답마다 하나씩

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

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
```

> `8`

<br>

- The "defualt" statement is used ...
  - ...때 "default" 문이 사용된다.

> `when no match is found`
>
> 일치하는 것이 없을 때

<br>