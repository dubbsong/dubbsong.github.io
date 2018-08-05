---
layout: post
title: "02. 이벤트 객체 (Events)"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com) jQuery 번역

<br>

# The Event Object

###### event 객체

<br>

- Every event handling function can receive an `event` object, which contains properties and methods related to the event:
  - 모든 이벤트 처리 함수는 이벤트와 관련된 속성 및 메소드를 포함하는  `event` 객체를 수신할 수 있다.
- `pageX`, `pageY` the mouse position (X & Y coordinates) at the time the event occurred, relative to the top left of the page.
  - `pageX`, `pageY`는 이벤트가 발생한 시점의 마우스 위치(X & Y 좌표)이며, 페이지의 왼쪽 상단을 기준으로 한다.

<br>

- `type`: the type of the event (e.g. "click").
  - 이벤트 type (예: "click").
- `which`: the button or key that was pressed.
  - 누른 버튼 또는 키.
- `data`: any data that was passed in when the event was bound.
  - 이벤트가 바인딩 될 때까지 전달된 모든 데이터.
- `target`: the DOM element that initiated the event.
  - 이벤트를 일으킨 DOM element.
- `preventDefault()`: prevent the default action of the event (e.g., following a link).
  - 이벤트의 기본 동작을 방지한다 (예: 링크 따라가기).
- `stopPropagation()`: stop the event from bubbling up to other elements.
  - 다른 element까지 bubbling 하지 않도록 이벤트를 중지한다.

<br>

> You can check out our JavaScript course for more information on event properties.
>
> 이벤트 속성에 대한 자세한 내용은 JavaScript 코스를 참조해라.

<br>

- For example, let's handle the click event on an \<a> element and prevent it from following the link provided in the href attribute:
  - 예를 들어, \<a> element에서 click 이벤트를 처리하고, href 속성에서 제공되는 링크를 따르지 않도록 해보자.

<br>

- HTML:

```html
<a href="https://www.sololearn.com">Click me</a>
```

<br>

- JS:

```js
$("a").click(function(event) {
   alert(event.pageX);
   event.preventDefault();
});
```

[코드 실행 확인 링크](https://code.sololearn.com/1131/#js)

<br>

- The code above alerts the mouse position at the time of the click and prevents following the link.
  - 위의 코드는 클릭할 때 마우스 위치를 알려주고, 링크를 따르지 않도록 방지한다.

<br>

> As you can see, the event object is passed to the event handler function as an argument.
>
> 보다시피, event 객체는 이벤트 핸들러 함수에 인수로 전달된다.

------

<br>

## Trigger Events

###### trigger 이벤트

<br>

- We can also trigger events programmatically using the `trigger()` method.
  - `trigger()` 메소드를 사용해서 이벤트를 프로그래밍 방식으로 trigger 할 수도 있다.
- For example, you can trigger a click event without the user actually clicking on an element:
  - 예를 들어, 사용자가 실제로 element를 클릭하지 않고 클릭 이벤트를 trigger 할 수 있다.

```js
$("div").click(function() {
   alert("Clicked!");
});

$("div").trigger("click");
```

[코드 실행 확인 링크](https://code.sololearn.com/1132/#js)

<br>

- This code triggers the click event for the selected element.
  - 이 코드는 선택한 element에 대한 클릭 이벤트를 trigger 한다.

<br>

> The `trigger()` method cannot be used to mimic native browser events, such as clicking on a file input box or an anchor tag.
>
> `trigger()` 메소드는 파일 input box나 anchor 태그를 클릭하는 등의 기본 브라우저 이벤트를 모방하는 데 사용할 수 없다.

> Only events in the jQuery event system can be handled.
>
> jQuery 이벤트 시스템의 이벤트만 처리할 수 있다.

------

<br>

## QUIZ

- Fill in the blanks to handle the keydown event on the input field and alert which key was pressed.
  - input field의 keydown 이벤트를 처리하고, 어떤 키가 눌렸는지 alert해라.

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