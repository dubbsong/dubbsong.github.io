---
layout: post
title: "09. form 유효성 검사 (DOM & Events)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript Form Validation

###### JavaScript Form 유효성 검사

<br>

- HTML5 adds some attributes that allow form validation.
  - HTML5는 form 유효성 검사를 허용하는 몇 가지 속성을 추가한다.
- For example, the `required` attribute can be added to an input field to make it mandatory to fill in.
  - 예를 들어, 반드시 기입해야 하는 `required` 속성을 input field에 추가할 수 있다.
- More complex form validation can be done using JavaScript.
  - JavaScript를 사용해서 보다 복잡한 form 유효성 검사를 수행할 수 있다.
- The form element has an `onsubmit` event that can be handled to perform validation.
  - form element에는 유효성 검사 수행을 처리할 수 있는 `onsubmit` 이벤트가 있다.
- For example, let's create a form with two inputs and one button.
  - 예를 들어, 두 개의 input과 하나의 버튼이 있는 form을 생성해보자.
- The text in both fields should be the same and not blank to pass the validation.
  - 유효성 검사를 통과하려면, 두 filed의 텍스트가 동일해야 하고, 공백이 아니어야 한다.

```html
<form onsubmit="return validate()" method="post">
   Number: <input type="text" name="num1" id="num1" />
   <br />
   Repeat: <input type="text" name="num2" id="num2" />
   <br />
   <input type="submit" value="Submit" />
</form>
```

<br>

- Now we need to define the `validate()` function:
  - 이제 `validate()` 함수를 정의해야 한다.

```js
function validate() {
   var n1 = document.getElementById("num1");
   var n2 = document.getElementById("num2");
   if (n1.value != "" && n2.value != "") {
      if (n1.value == n2.value) {
         return true;
      }
   }
   alert("The values should be equal and not blank");
   return false;
}
```

[코드 실행 확인 링크](https://code.sololearn.com/966/#js)

<br>

- We return `true` only when the values are not blank and are equal.
  - 값이 공백이 아니고 동등한 경우에만 `true`를 반환한다.

<br>

> The form will not get submitted if its `onsubmit` event returns `false`.
>
> `onsubmit` 이벤트가 `false`를 반환하면 form이 제출되지 않는다.

------

<br>

## QUIZ

- The form will submit to its action if onsubmit returns:
  - form은 onsubmit이 …을 반환하는 경우에 제출된다.

> `true`

<br>