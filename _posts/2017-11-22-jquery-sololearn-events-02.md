---
layout: post
title: "(Events 02) 이벤트 객체"
categories: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

# jQuery Event Object

###### 이벤트 객체

<br>

- Every event handling function can receive an `event object`, which contains properties and methods related to the event:
  - 모든 이벤트 핸들링 함수는 이벤트와 관련된 속성과 메소드를 포함하는 `이벤트 객체`를 수신할 수 있다.
- `pageX`, `pageY` the mouse position (X & Y coordinates) at the time the event occurred, relative to the top left of the page.
  - `pageX`, `pageY`는 이벤트가 발생한 시점의 마우스 위치(X & Y 좌표)이며, 페이지의 왼쪽 상단을 기준으로 한다.

<br>

- `type`: the type of the event (e.g. "click").
  - 이벤트 type (예: "click")
- `which`: the button or key that was pressed.
  - 누른 버튼 또는 key
- `data`: any data that was passed in when the event was bound.
  - 이벤트가 binding 될 때 전달된 모든 데이터
- `target`: the DOM element that initiated the event.
  - 이벤트를 시작한 DOM element
- `preventDefault()`: prevent the default action of the event (e.g., following a link).
  - 이벤트의 기본 동작을 방지한다.
  - (예: link 따라가기)
- `stopPropagation()`: stop the event from bubbling up to other elements.
  - 이벤트가 다른 element까지 bubbling 하는 것을 멈춘다.

<br>

- For example, let's handle the click event on an \<a> element and prevent it from following the link provided in the href attribute:
  - 예를 들어 \<a> element에서 click 이벤트를 처리하고, href 속성에서 제공하는 link를 따르지 못하도록 해보자.

<br>

- HTML:

```html
<a href="https://www.sololearn.com">Click me</a>
```

<br>

- JS:

```js
$(function() {
   $("a").click(function(event) {
      alert(event.pageX);
      event.preventDefault();
   });
});
```

[코드 실행 확인](https://code.sololearn.com/1131/#js)

<br>

- The code above alerts the mouse position at the time of the click and prevents following the link.
  - 위 코드는 클릭할 때의 마우스 위치를 alert 하고, link를 따르지 않도록 한다.

<br>

> As you can see, the event object is passed to the event handler function as an argument.
>
> 보다시피, 이벤트 객체는 이벤트 핸들러 함수에 인수로 전달된다.

------

<br>

## Trigger Events

###### 이벤트 trigger(작동, 촉발)

<br>

- We can also trigger events programmatically using the `trigger()` method.
  - `trigger()` 메소드를 사용해서 이벤트를 프로그래밍 방식으로 trigger 할 수도 있다.
- For example, you can trigger a click event without the user actually clicking on an element.
  - 예를 들어, 사용자가 element를 실제로 클릭하게 하지 않고 click 이벤트를 trigger 할 수 있다.

```js
$(function() {
   $("div").click(function() {
      alert("Clicked!");
   });
   $("div").trigger("click");
});
```

[코드 실행 확인](https://code.sololearn.com/1132/#js)

<br>

- This code triggers the click event for the selected element.
  - 이 코드는 선택한 element에 대한 click 이벤트를 trigger 한다.

<br>

> The `trigger()` method cannot be used to mimic native browser events, such as clicking on a file input box or anchor tag.
>
> `trigger()` 메소드는 file input 상자나 anchor 태그를 클릭하는 것과 같이, 기본 브라우저를 모방하는 데 사용할 수 없다.

> Only events in the jQuery event system can be handled.
>
> jQuery 이벤트 시스템의 이벤트만 처리할 수 있다.

------

<br>

## QUIZ

- Fill in the blanks to handle the keydown event on the input field and alert which key was pressed.
  - input field에 keydown 이벤트를 처리하고, 어떤 key가 눌렸는지 alert 해라.

```js
$("input").keydown(function(event) {
   alert(event.which);
});
```

<br>

- Fill in the blanks to trigger the submit event on the selected element.
  - 선택한 element에서 submit 이벤트를 trigger 해라.

```js
$("form").trigger("submit");
```

<br>