---
layout: post
title: "03. if/else if/else 문 (Conditionals and Loops)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript if/else if/else Statement

###### JavaScript if/else if/else 문

------

<br>

<br>

## else if

###### else if 문

<br>

- You can use the `else if statement` to specify a new condition if the first condition is false.
  - `else if 문`을 사용해서 첫 번째 조건이 false인 경우에 새 조건을 지정할 수 있다.

<br>

- Example:

```js
var course = 1;
if (course == 1) {
   document.write("<h1>HTML Tutorial</h1>");
} else if (course == 2) {
   document.write("<h1>CSS Tutorial</h1>");
} else {
   document.write("<h1>JavaScript Tutorial</h1>");
}
```

[코드 실행 확인 링크](https://code.sololearn.com/663/#js)

<br>

- `if` course is equal to 1, output "HTML Tutorial".
  - `if` course가 1이라면, "HTML Tutorial"을 출력한다.
- `else if` course is equal to 2, output "CSS Tutorial".
  - `else if` course가 2라면, "CSS Tutorial"을 출력한다.
- If none of the above condition is true, then output "JavaScript Tutorial".
  - 위의 조건 중 어느 것도 true가 아니면, "JavaScript Tutorial"을 출력한다.

<br>

- `course` is equal to 1, so we get the following result:
  - `course`는 1과 같으므로, 다음 결과를 얻는다.

![sololearn img](/assets/img/sololearn-js-conditionals and loops-03-01.png)

<br>

> The final `else` statement "ends" the else if statement and should be always written after the `if` and `else if` statements.
>
> 마지막 `else` 문은 else if 문을 "종료"하며, 항상 `if` 문과 `else if` 문 뒤에 작성해야 한다.

<br>

<br>

- The final `else` block will be executed when `none` of the conditions is true.
  - 마지막 `else` 블록은 true 조건이 없을 때 실행된다.

<br>

- Let's change the value of the `course` variable in our previous example.
  - 이전 예제의 `course` 변수 값을 변경해보자.

```js
var course = 3;
if (course == 1) {
   document.write("<h1>HTML Tutorial</h1>");
} else if (course == 2) {
   document.write("<h1>CSS Tutorial</h1>");
} else {
   document.write("<h1>JavaScript Tutorial</h1>");
}
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-js-conditionals and loops-03-02.png)

<br>

> You can write as many `else if` statements as you need.
>
> 필요한 만큼 `else if` 문을 작성할 수 있다.

------

<br>

## QUIZ

- What keyword is used to end the "else if" statement?
  - "else if" 문을 끝내는 데 사용되는 키워드는 무엇인가?

> `else`

<br>

- Fill in the blanks to create a valid if...else...if statement:
  - 유효한 if...else...if 문을 생성해라.

```js
var status = 1;
var msg;
if (status == 1) {
   msg = "Online";
} else if {
   msg = "Away";
} else {
   msg = "Offline";
}
```

<br>