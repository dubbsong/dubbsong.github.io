---
layout: post
title: "(Functions 05) alert/prompt/confirm 팝업 상자"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

# JavaScript alert/prompt/confirm popup boxes

###### alert/prompt/confirm 팝업 상자

------

<br>

<br>

## The alert Box

###### alert 상자

<br>

- JavaScript offers three types of popup boxes, the `alert`, `prompt`, and `confirm` boxes.
  - JavaScript는 `alert`, `prompt`, `confirm` 세 가지 type의 팝업 상자를 제공한다.

<br>

- An `alert box` is used when you want to ensure that information gets through to the user.
  - 사용자에게 정보를 전달할 때 `alert 상자`가 사용된다.
- When an alert box pops up, the user must click OK to proceed.
  - alert 상자가 나타나면, 사용자가 OK를 클릭해서 계속 진행해야 한다.
- The `alert` function takes a single parameter, which is the text displayed in the popup box.
  - `alert` 함수는 팝업 상자에 표시되는 텍스트인 하나의 매개변수를 사용한다.

<br>

- Example:

```js
alert("Do you really want to leave this page?");
```

[코드 실행 확인](https://code.sololearn.com/682/#js)

<br>

- Result:

![img](/assets/img/js-sololearn-functions-05-01.png)

<br>

- To display `line breaks` within a popup box, use a backslash followed by the character n.
  - 팝업 상자의 `줄 바꿈`을 표시하려면, backslash(\\) 다음에 문자 n을 사용한다.

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
> 팝업 상자를 사용할 때에는 사용자가 OK를 클릭한 후에만 페이지를 계속 사용할 수 있으므로 주의해라.

------

<br>

## The prompt Box

###### prompt 상자

<br>

- A `prompt box` is often used to have the user input a value before entering a page.
  - `prompt 상자`는 사용자가 페이지에 들어가기 전에 값을 입력하게 하는 데 종종 사용된다.
- When a prompt box pops up, the user will have to click either OK or Cancel to proceed after entering the input value.
  - prompt 상자가 나타나면, 사용자는 입력 값을 입력한 후에 OK 또는 Cancel을 클릭해야 한다.
- If the user clicks OK, the box `returns the input value`.
  - 사용자가 OK를 클릭하면, 상자는 `입력 값을 반환한다`.
- If the user clicks Cancel, the box returns `null`.
  - 사용자가 Cancel을 클릭하면, 상자는 `null`을 반환한다.

<br>

- The `prompt()` method takes `two parameters`.
  - `prompt()` 메소드는 `두 개의 매개변수`를 사용한다.

<br>

1. The first is the label, which you want to display in the text box.
   - 첫 번째는 텍스트 상자에 표시할 label이다.
2. The second is a default string to display in the text box (optional).
   - 두 번째는 텍스트 상자에 표시할 기본 문자열이다. (선택 사항)

<br>

- Example:

```js
var user = prompt("Please enter your name");
alert(user);
```

[코드 실행 확인](https://code.sololearn.com/684/#js)

<br>

- The prompt appears as:
  - prompt가 다음과 같이 나타난다.

![img](/assets/img/js-sololearn-functions-05-03.png)

<br>

> When a prompt box pops up, the user will have to click either "OK" or "Cancel" to proceed after entering an input value.
>
> prompt 상자가 나타나면, 사용자는 입력 값을 입력한 후에 "OK" 또는 "Cancel"을 클릭해야 한다.

> Do not overuse this method, because it prevents the user from accessing other parts of the page until the box is closed.
>
> 상자가 닫힐 때까지 사용자가 페이지의 다른 부분에 액세스하는 것을 방지하기 때문에, 이 메소드를 과도하게 사용하지 마라.

------

<br>

## The confirm Box

###### confirm 상자

<br>

- A `confirm box` is often used to have the user verify or accept something.
  - `confirm 상자`는 사용자가 무언가를 확인하거나 수락하도록 하기 위해 종종 사용된다.
- When a confirm box pops up, the user must click either OK or Cancel to proceed.
  - confirm 상자가 나타나면, 사용자가 OK 또는 Cancel을 클릭해서 계속 진행해야 한다.
- If the user clicks OK, the box returns `true`.
  - 사용자가 OK를 클릭하면, 상자는 `true`를 반환한다.
- If the user clicks Cancel, the box returns `false`.
  - 사용자가 Cancel을 클릭하면, 상자는 `false`를 반환한다.

<br>

- Example:

```js
var result = confirm("Do you really want to leave this page?");

if (result == true) {
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
  - 사용자가 `OK`를 클릭했을 때의 결과:

![img](/assets/img/js-sololearn-functions-05-05.png)

<br>

- The result when the user clicks `Cancel`:
  - 사용자가 `Cancel`을 클릭했을 때의 결과:

![img](/assets/img/js-sololearn-functions-05-06.png)

<br>

> Do not overuse this method, because it also prevents the user from accessing other parts of the page until the box is closed.
>
> 상자가 닫힐 때까지 사용자가 페이지의 다른 부분에 액세스하는 것을 방지하기 때문에, 이 메소드를 과도하게 사용하지 마라.

------

<br>

## QUIZ

- How many parameters can be accepted by the "alert" function?
  - "alert" 함수로 수용할 수 있는 매개변수의 수는 얼마인가?

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
  - "confirm" 대화 상자에서 "OK"는 true를 반환하고, "Cancel"은 …를 반환한다.

> `false`

<br>