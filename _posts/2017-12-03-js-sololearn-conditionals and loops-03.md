---
layout: post
title: "SoloLearn 번역 - 03. The if/else if/else Statement (Conditionals and Loops)"
categories: javascript
tags: JS
---

## else if (else if 문)

- You can use the **else if statement** to specify a new condition if the first condition is false.
  - 첫 번째 조건이 false일 경우, **else if 문**을 사용해서 새 조건을 지정할 수 있다.

<br>

- Example:

```js
var course = 1;

if (course == 1) {
   document.write("<h1>HTML Tutorial</h1>");
} else if (course == 2) {
   document.write("<h1>CSS Tutorial</h1>");
} else {
   document.write("<h1>JavaScript Tutorial</h1>";)
}
```

<br>

- The above code says:
  - 위의 코드는 다음과 같다.

<br>

1. **if** course is equal to 1, output "HTML Tutorial".
   - course가 1과 같은 경우, "HTML Tutorial"을 출력해라.
2. **else if**, course is equal to 2, output "CSS Tutorial".
   - course가 2와 같은 경우, "CSS Tutorial"을 출력해라.
3. if none of the above condition is true, then output "JavaScript Tutorial".
   - 위의 조건 중 어느 것도 true가 아니면, "JavaScript Tutorial"을 출력해라.

<br>

- **course** is equal to 1, so we get the following result:
  - **course**가 1과 같으므로, 다음 결과를 얻는다.

![SoloLearn img](/assets/img/sololearn-js-conditionals and loops-03-01.png)

<br>

> The final **else** statement "ends" the else if statement and should be always written after the **if** and **else if** statements.
>
> 마지막 **else** 문은 else if 문을 "종료"하며, 항상 **if** 및 **else if** 문 다음에 작성해야 한다.

------

<br>

## else if 02

- The final **else** block will be executed when **none** of the conditions is true.
  - 마지막 **else** 블록은 true인 조건이 하나도 없을 때 실행된다.

<br>

- Let's change the value of the **course** variable in our previous example.
  - 이전 예제에서 **course** 변수의 값을 바꿔보자.

```js
var course = 3;

if (course == 1) {
   document.write("<h1>HTML Tutorial</h1>");
} else if (course == 2) {
   document.write("<h1>CSS Tutorial</h1>");
} else {
   document.write("<h1>JavaScript Tutorial</h1>";)
}
```

<br>

- The result:

![SoloLearn img](/assets/img/sololearn-js-conditionals and loops-03-02.png)

<br>

> You can write as many **else if** statements as you need.
>
> 필요한 만큼 **else if** 문을 작성할 수 있다.

------

<br>

## QUIZ

- What keyword is used to end the "else if" statement?
  - stop
  - **else**
  - end

<br>

- Fill in the blanks to create a valid if...else...if statement:

```js
var status = 1;
var msg;

if (status == 1) {
   msg = "Online";
} else if (status == 2) {
   msg = "Away";
} else {
   msg = "Offline";
}
```

<br>