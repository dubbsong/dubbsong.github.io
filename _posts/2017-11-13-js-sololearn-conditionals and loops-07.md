---
layout: post
title: "07. do...while loop (Conditionals and Loops)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript do...while loop

###### JavaScript do...while 반복문

<br>

- The `do...while` loop is a variant of the while loop.
  - `do...while` loop는 while loop의 변형이다.
- This loop will execute the code block once, `before` checking if the condition is true, and then it will repeat the loop as long as the condition is true.
  - 이 loop는 조건이 true인 경우를 확인하기 전에 코드 블록을 한 번 실행한다.
  - 그런 다음, 조건이 true인 동안 loop를 반복한다.

<br>

- Syntax:

```js
do {
   코드 블록
}
while (condition);
```

<br>

> Note the `semicolon` used at the end of the do...while loop.
>
> do...while loop의 끝에 사용되는 `세미콜론`에 주의해라.

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

[코드 실행 확인 링크](https://code.sololearn.com/672/#js)

<br>

- This prints out numbers from 20 to 25.
  - 이는 20에서 25까지의 숫자를 출력한다.

![sololearn img](/assets/img/sololearn-js-conditionals and loops-07-01.png)

<br>

> The loop will always be executed `at least once`, even if the condition is false, because the code block is executed before the condition is tested.
>
> 코드 블록은 조건이 테스트되기 전에 실행되므로, 조건이 false인 경우, loop는 항상 `적어도 한 번` 실행된다.

------

<br>

## QUIZ

- Apply the "do" and "while" keywords in their corresponding positions.
  - 알맞은 위치에 "do"와 "while" 키워드를 적용해라.

```js
var count = 1;
do {
   document.write("hello <br />");
   count++;
}
while (count <= 10);
```

<br>