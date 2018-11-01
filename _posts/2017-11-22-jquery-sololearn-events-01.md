---
layout: post
title: "(Events 01) 이벤트 핸들링"
categories: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

# jQuery Handling Events

###### 이벤트 핸들링

<br>

- jQuery provides an efficient way to handle events.
  - jQuery는 이벤트를 효율적으로 처리하는 방법을 제공한다.
- Events occur when the user performs an action, such as clicking an element, moving the mouse, or submitting a form.
  - 이벤트는 사용자가 element를 클릭하거나, 마우스를 움직이거나, form을 제출하는 등의 작업을 수행할 때 발생한다.
- When an event occurs on a target element, a `handler function` is executed.
  - target element에서 이벤트가 발생하면, `핸들러 함수`가 실행된다.
- For example, let's say we want to handle the `click` event on an element with id="demo" and display the current date when the button is clicked.
  - 예들 들어 id="demo" element에서 `click` 이벤트를 처리하고, 버튼을 클릭했을 때 현재 날짜를 표시한다고 가정해보자.
- Using pure JavaScript, the code looks like:
  - 순수 JavaScript를 사용하면, 코드는 다음과 같다.

```js
var x = document.getElementById("demo");
x.onclick = function() {
   document.body.innerHTML = Date();
}
```

[코드 실행 확인](https://code.sololearn.com/1126/#js)

<br>

- The same event could be handled using jQuery with the following code:
  - jQuery를 사용해서 동일한 이벤트를 다음 코드로 처리할 수 있다.

```js
$(function() {
   $("#demo").click(function() {
      $("body").html(Date());
   });
});
```

[코드 실행 확인](https://code.sololearn.com/1127/#js)

<br>

- As you can see, the jQuery code is shorter and easier to read and write.
  - 보다시피 jQuery 코드는 읽거나 작성하기에 짧고 쉽다.
- Notice, that the event name is provided without the "on" prefix (i.e., `onclick` in JavaScript is `click` in jQuery).
  - 이벤트 이름은 "on" 접두사 없이 제공된다.
  - (JavaScript의 `onclick`은 jQuery에서 `click`이다)

<br>

> The function that is executed when an event is fired is called the `event handler`.
>
> 이벤트가 발생했을 때 실행되는 함수를 `이벤트 핸들러`라고 한다.

------

<br>

## Common Events

###### 일반적인 이벤트

<br>

- The following are the most commonly used events:
  - 다음은 가장 일반적으로 사용되는 이벤트이다.

<br>

#### Mouse Events:

###### 마우스 이벤트

<br>

- `click`: occurs when an element is clicked.
  - element가 클릭될 때 발생한다.
- `dbclick`: occurs when an element is double-clicked.
  - element가 두 번 클릭될 때 발생한다.
- `mouseenter`: occurs when the mouse pointer is over (enters) the selected element.
  - 마우스 포인터가 선택한 element 위에 있을 때 발생한다.
- `mouseleave`: occurs when the mouse pointer leaves the selected element.
  - 마우스 포인터가 선택한 element를 벗어날 때 발생한다.
- `mouseover`: occurs when the mouse pointer is over the selected element.
  - 마우스 포인터가 선택한 element 위에 있을 때 발생한다.

<br>

#### Keyboard Events:

###### 키보드 이벤트

<br>

- `keydown`: occurs when a keyboard key is pressed down.
  - 키보드 key를 누르면 발생한다.
- `keyup`: occurs when a keyboard key is released.
  - 키보드 key를 놓으면 발생한다.

<br>

#### Form Events:

###### form 이벤트

<br>

- `submit`: occurs when a form is submitted.
  - form 제출 시에 발생한다.
- `change`: occurs when the value of an element has been changed.
  - element의 값이 변경되면 발생한다.
- `focus`: occurs when an element gets focus.
  - element가 focus를 얻으면 발생한다.
- `blur`: occurs when an element loses focus.
  - element가 focus를 잃으면 발생한다.

<br>

#### Document Events:

###### document 이벤트

<br>

- `ready`: occurs when the DOM has been loaded.
  - DOM이 로딩될 때 발생한다.
- `resize`: occurs when the browser window changes size.
  - 브라우저 창이 크기를 변경하면 발생한다.
- `scroll`: occurs when the user scrolls in the specified element.
  - 사용자가 지정된 element에서 스크롤 할 때 발생한다.

<br>

- As an example, let's change the content of a div when the user types in an input field.
  - 예를 들어 사용자가 input field에 입력할 때, div의 content를 변경해보자.
- To do that, we need to handle the `keydown` event, which occurs when a key on the keyboard is pressed:
  - 이렇게 하려면 키보드의 key를 누를 때 발생하는 `keydown` 이벤트를 처리해야 한다.

<br>

- HTML:

```html
<input type="text" id="name" />
<div id="msg"></div>
```

<br>

- JS:

```js
$(function() {
   $("#name").keydown(function() {
      $("#msg").html($("#name").val());
   });
});
```

[코드 실행 확인](https://code.sololearn.com/1128/#js)

<br>

- The code above handles the `keydown` event for the element with id="name" and assigns the content of the div with id="msg" the value of the input field.
  - 위 코드는 id="name" element에 대한 `keydown` 이벤트를 처리하고, id="msg" div의 content를 input field의 값으로 할당한다.

------

<br>

## Handling Events

###### 이벤트 핸들링

<br>

- Another way to handle events in jQuery is by using the `on()` method.
  - jQuery에서 이벤트를 처리하는 또 다른 방법은, `on()` 메소드를 사용하는 것이다.
- The `on()` method is used to attach an event to the selected element.
  - `on()` 메소드는 선택한 element에 이벤트를 첨부하는 데 사용된다.

<br>

- For example:

```js
$(function() {
   $("p").on("click", function() {
      alert("clicked");
   });
});
```

[코드 실행 확인](https://code.sololearn.com/1129/#js)

<br>

- As you can see, the event name is passed as the first argument to the `on()` method.
  - 보다시피, 이벤트 이름은 `on()` 메소드의 첫 번째 인수로 전달된다.
- The second argument is the handler function.
  - 두 번째 인수는 핸들러 함수이다.

<br>

> The `on()` method is useful for binding the same handler function to multiple events.
>
> `on()` 메소드는 동일한 핸들러 함수를 여러 이벤트에 binding 하는 데 유용하다.

> You can provide multiple event names separated by `spaces` as the first argument.
>
> `공백`으로 구분된 여러 이벤트 이름을 첫 번째 인수로 제공할 수 있다.

> For example, you could use the same event handler for the `click` and `dbclick` events.
>
> 예를 들어 `click`과 `dbclick` 이벤트에 동일한 이벤트 핸들러를 사용할 수 있다.

------

<br>

## off()

###### off() 메소드

<br>

- You can remove event handlers using the `off()` method.
  - `off()` 메소드를 사용해서 이벤트 핸들러를 제거할 수 있다.

<br>

- For example:

```js
$(function() {
   $("div").on("click", function() {
      alert('Hi there!');
   });
   $("div").off("click");
});
```

[코드 실행 확인](https://code.sololearn.com/1130/#js)

<br>

> The argument of the `off()` method is the event name you want to remove the handler for.
>
> `off()` 메소드의 인수는 핸들러를 제거하려는 이벤트 이름이다.

------

<br>

## QUIZ

- The event handler is a:
  - 이벤트 핸들러는 다음과 같다.

> `function`
>
> 함수

<br>

- Fill in the blanks to handle the click event on the paragraph tag.
  - \<p> 태그의 click 이벤트를 처리해라.

```js
$("p").click(function() {
   alert("Clicked!");
});
```

<br>

- Fill in the blanks to handle the submit event for the form element using the on() method:
  - on() 메소드를 사용해서 form element에 대한 submit 이벤트를 처리해라.

```js
$("form").on("submit", function() {
   // some code
});
```

<br>

- Fill in. the blanks to remove the event handler for the focus event on the element with id="test".
  - id="test" element에서 focus 이벤트에 대한 이벤트 핸들러를 제거해라.

```js
$("#test").off("focus");
```

<br>