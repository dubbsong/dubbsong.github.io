---
layout: post
title: "(Function 06) Module 4 Quiz"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## QUIZ

- The following code will result in what value?
  - 다음 코드는 어떤 값이 결과로 나타나는가?

```js
function test(number) {
   while (number < 5) {
      number++;
   }
   return number;
}

alert(test(2));
```

> `5`

<br>

- What is the output of the following expression?
  - 다음 표현식의 출력은 무엇인가?

```js
function multNmbrs(a, b) {
   var c = a * b;
}

multNmbrs(2, 6);
```

> `Nothing`

<br>

- Please fill in the corresponding names for the built-in dialog boxes:
  - 내장된 대화 상자의 해당 이름을 입력해라.

> `prompt is for getting input from the user;`
>
> `alert is for displaying a message in a box;`

<br>

- Fill in the blanks to calculate the maximum of the parameters:
  - 매개변수의 최대값을 계산해라.

```js
function max(a, b) {
   if (a >= b)
      return a;
   else
      return b;
}
```

<br>

- What is the correct syntax for referring to an external script called "script.js"?
  - "script.js"라는 외부 script를 참조하기 위한 올바른 구문은 무엇인가?

> `<script src="script.js">`

<br>

- What alert will display on the screen?
  - 화면에 어떤 alert가 표시되는가?

```js
function test(a, b) {
   if (a > b) {
      return a * b;
   } else {
      return b / a;
   }
}

alert(test(5, 15));
```

> `3`

<br>