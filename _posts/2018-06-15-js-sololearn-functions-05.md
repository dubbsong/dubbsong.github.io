---
layout: post
title: "(Functions 05) alert, prompt, confirm"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## Alert Box

###### alert

<br>

- JavaScript offers three types of popup boxes, the `alert`, `prompt`, and `confirm` boxes.
  - JavaScript는 세 가지 type의 팝업 상자를 제공한다: `alert`, `prompt`, `confirm`

<br>

- An `alert box` is used when you want to ensure that information gets through to the user.
  - 정보를 사용자에게 전달하기 위해 `alert`가 사용된다.
- When an alert box pops up, the user must click OK to preceed.
  - alert가 나타나면, 사용자가 OK를 클릭해서 계속 진행해야 한다.
- The `alert` function takes a single parameter, which is the text displayed in the popup box.
  - `alert` 함수는 하나의 매개변수를 사용한다.
  - 이 매개변수는 팝업 상자에 표시되는 텍스트다.

```js
alert("Do you really want to leave this page?");
```

[코드 실행 확인](https://code.sololearn.com/682/#js)

<br>

- Result:

![img](/assets/img/js-sololearn-functions-05-01.png)

<br>

- To display `line breaks` within a popup box, use a backslash followed by the character n.
  - 팝업 상자 내에서 `줄 바꿈`을 나타내려면, 백슬래시 다음에 문자 n을 사용한다.

```js
alert("Hello\nHow are you?");
```

[코드 실행 확인](https://code.sololearn.com/683/#js)

<br>

- Result:

![img](/assets/img/js-sololearn-functions-05-02.png)

<br>

> Be careful when using alert boxes, as the user can continue using the page only after clicking OK.
>
> alert는 사용자가 OK를 클릭한 후에만 페이지를 계속 사용할 수 있으므로 사용에 유의해라.

------

<br>

## Prompt Box

###### prompt

<br>

- A `prompt box` is often used to have the user input a value before entering a page.
  - `prompt`는 페이지에 들어가기 전 사용자가 값을 입력하는 데 종종 사용된다.
- When a prompt box pops up, the user will have to click either OK or Cancel to proceed after entering the input value.
  - promp가 나타나면, 사용자는 입력 값을 입력한 후 OK 또는 Cancel을 클릭해야 한다.
- If the user clicks OK, the box `returns the input value`.
  - 사용자가 OK를 클릭하면 `입력 값이 반환된다`.

<br>

- The `prompt()` method takes `two parameters`.
  - `prompt()` 메소드는 `두 개의 매개변수`를 사용한다.
- The first is the label, which you want to display in the text box.
  - 첫 번째는 텍스트 상자에 표시할 label이다.
- The second is a default string to display in the text box (optional).
  - 두 번째는 텍스트 상자에 표시할 기본 문자열이다.
  - (선택 사항)

```js
var user = prompt("Please enter your name");
alert(user);
```

[코드 실행 확인](https://code.sololearn.com/684/#js)

<br>

- The prompt appears are:
  - prompt는 다음과 같이 나타난다.

![img](/assets/img/js-sololearn-functions-05-03.png)

<br>

> When a prompt box pops up, the user will have to click either "OK" or "Cancel" to proceed after entering an input value.
>
> prompt가 나타나면, 사용자는 입력 값을 입력한 후 OK 또는 Cancel을 클릭해야 한다.

> Do not overuse this method, because it prevents the user from accessing other parts of the page until the box is closed.
>
> 이 메소드를 과도하게 사용하지 마라.
>
> 상자가 닫힐 때까지 사용자가 다른 부분에 액세스하는 것을 방해하기 때문이다.

------

<br>

## Confirm Box

###### confirm

<br>

- A `confirm box` is often used to have the user verify or accept something.
  - `confirm`은 사용자가 무언가를 확인하거나 수락하도록 하는 데 종종 사용된다.
- When a confirm box pops up, the user must click either OK or Cancel to proceed.
  - confirm이 나타나면, 사용자는 계속 진행하기 위해 OK 또는 Cancel을 클릭해야 한다.
- If the user clicks OK, the box returns `true`.
  - 사용자가 OK를 클릭하면 `true`를 반환한다.
- If the user clicks Cancel, the box returns `false`.
  - 사용자가 Cancel을 클릭하면 `false`를 반환한다.

```js
var result = confirm("Do you really want to leave this page?");

if (result === true) {
   alert("Thanks for visiting");
} else {
   alert("Thanks for staying with us");
}
```

[코드 실행 확인](https://code.sololearn.com/685/#js)

<br>

- Result:

![img](/assets/img/js-sololearn-functions-05-04.png)

<br>

- The result when the user clicks `OK`:
  - 사용자가 `OK`를 클릭했을 때:

![img](/assets/img/js-sololearn-functions-05-05.png)

<br>

- The result when the user clicks `Cancel`:
  - 사용자가 `Cancel`을 클릭했을 때:

![img](/assets/img/js-sololearn-functions-05-06.png)

<br>

> Do not overuse this method, because it also prevents the user from accessing other parts of the page until the box is closed.
>
> 이 메소드를 과도하게 사용하지 마라.
>
> 상자가 닫힐 때까지 사용자가 다른 부분에 액세스하는 것을 방해하기 때문이다.

------

<br>

## QUIZ

- How many parameters can be accepted by the "alert" function?
  - "alert" 함수로 수용할 수 있는 매개변수는 몇 개인가?

> `1`

<br>

- Fill in the blanks to obtain the name of the user and alert it to the screen:
  - 사용자의 이름을 얻고, 화면에 alert 해라.

```js
var name = prompt("Enter your name:");
alert(name);
```

<br>

- In the "confirm" dialog box, "OK" returns true, and "Cancel" returns ...
  - "confirm" 대화 상자에서 "OK"는 true를 반환하고, "Cancel"은 ...를 반환한다.

> `false`

<br>