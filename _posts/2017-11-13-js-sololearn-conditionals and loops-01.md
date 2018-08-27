---
layout: post
title: "01. if 문 (Conditionals and Loops)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript if Statement

###### JavaScript if 문

<br>

- Very often when you write code, you want to perform different actions based on different conditions.
  - 코드를 작성할 때, 다른 조건에 따라 다른 작업을 수행하려는 일이 매우 자주 일어난다.
- You can do this by using `conditional statements` in your code.
  - 코드에서 `조건문`을 사용해서 이 작업을 수행할 수 있다.

<br>

- Use `if` to specify a block of code that will be executed if a specified condition is true.
  - 지정된 조건이 true일 경우, 실행될 코드 블록을 지정하려면 `if`를 사용해라.

```js
if (condition) {
   statements
}
```

<br>

- The statements will be executed only if the specified condition is `true`.
  - 지정한 조건이 `true`인 경우에만 명령문이 실행된다.

<br>

- Example:

```js
var myNum1 = 7;
var myNum2 = 10;
if (myNum1 < myNum2) {
   alert("JavaScript is easy to learn.");
}
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-js-conditionals and loops-01-01.png)

<br>

> As seen in the picture above, the JavaScript `alert()` method is used to generate a popup alert box that contains the information provided in parentheses.
>
> 위 그림에서 알 수 있듯이, JavaScript `alert()` 메소드는 괄호 안에 제공된 정보를 포함하는 팝업 alert 박스를 생성하는 데 사용된다.

<br>

<br>

- This is another example of a `false` conditional statement.
  - 이것은 `false` 조건문의 또 다른 예제이다.

```js
var myNum1 = 7;
var myNum2 = 10;
if (myNum1 > myNum2) {
   alert("JavaScript is easy to learn.");
}

// 코드가 실행되지 않는다.
```

[코드 실행 확인 링크](https://code.sololearn.com/661/#js)

<br>

- As the condition evaluates to false, the alert statement is skipped and the program continues with the line after the if statement's closing curly brace.
  - 조건이 false로 평가되면, alert 문을 건너뛰고, 프로그램은 if 문의 닫는 중괄호 다음에 계속된다.

<br>

> Note that `if` is in lowercase letters.
>
> `if`는 소문자다.

> Uppercase letters (If or IF) will generate an error.
>
> 대문자(If 또는 IF)는 에러를 발생시킨다.

------

<br>

## QUIZ

- Please add the corresponding characters to complete the statement:
  - 명령문을 완성하기 위해 해당 문자를 추가해라.

```js
if (var1 > var2) {
   document.write("OK");
}
```

<br>

- What happens if the tested condition is false?
  - 테스트 조건이 false면 어떤 일이 일어나는가?

> `The code does nothing and moves to the next section`
>
> 코드는 아무것도 하지 않고, 다음 섹션으로 이동한다.

<br>