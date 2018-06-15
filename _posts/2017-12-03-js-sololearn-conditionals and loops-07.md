---
layout: post
title: "SoloLearn 번역 - 07. The Do...While Loop (Conditionals and Loops)"
categories: javascript
tags: JS
---

## The Do...While Loop

- The **do...while** loop is a variant of the while loop.
  - **do...while** loop는 while loop의 변형이다.
- This loop will execute the code block once, **before** checking if the condition is true, and then it will repeat the loop as long as the condition is true.
  - 이 loop는 조건이 true인지 확인하기 전에 코드 블록을 한 번 실행한 다음, 조건이 true인 한 loop를 반복한다.

<br>

- Syntax:

```js
do {
   code block
}

while (condition);
```

<br>

> Note the **semicolon** used at the end of the do...while loop.
>
> do...while loop의 끝에서 사용되는 **semicolon**에 신경써라.

<br>

- Example:

```js
var i = 20;

do {
   document.write(i + "<br />");
   i++;
}

while (i <= 25);
```

<br>

- This prints out numbers from 20 to 25.
  - 20부터 25까지의 숫자를 출력한다.

![SoloLearn img](/assets/img/sololearn-js-conditionals and loops-07-01.png)

<br>

> The loop will always be executed **at least once**, even if the condition is false, because the code block is executed before the condition is tested.
>
> 코드 블록은 조건이 테스트 되기 전에 실행되기 때문에, loop는 조건이 false인 경우에도, 항상 **적어도 한 번** 실행된다.

------

<br>

## QUIZ

- Apply the "do" and "while" keywords in their corresponding positions.

```js
var count = 1;

do {
   document.write("hello <br />");
   count++;
}

while (count <= 10);
```

<br>