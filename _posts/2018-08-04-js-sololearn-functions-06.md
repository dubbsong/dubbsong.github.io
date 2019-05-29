---
layout: post
title: "(Function 06) Module 4 Quiz"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## QUIZ

- The following code will result in what value?
  - 다음 코드는 어떤 값을 출력하는가?

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

- Fill in the blanks to calculate the maximum of the parameters:
  - 매개변수의 최댓값을 계산해라.

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

```html
<script src="script.js"></script>
```

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