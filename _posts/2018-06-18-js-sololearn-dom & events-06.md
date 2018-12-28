---
layout: post
title: "(DOM & Events 06) 이벤트 핸들링"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## Events

###### 이벤트

<br>

- You can write JavaScript code that executes when an `event` occurs, such as when a user clicks an HTML element, moves the mouse, or submits a form.
  - 사용자가 HTML element를 클릭하거나, 마우스를 움직이거나, form을 제출하는 경우와 같이, `이벤트`가 발생할 때 실행되는 JavaScript 코드를 작성할 수 있다.
- When an event occurs on a target element, a `handler` function is executed.
  - target element에서 이벤트가 발생하면 `핸들러` 함수가 실행된다.
- Common HTML events include:
  - 일반적인 HTML 이벤트는 다음과 같다.

<br>

- onclick: occurs when the user clicks on an element
  - 사용자가 element를 클릭할 때 발생한다.
- onload: occurs when an object has loaded
  - 객체가 로딩될 때 발생한다.
- onunload: occurs once a page has unloaded (for \<body>)
  - 페이지가 언로딩(\<body>의 경우) 되면 발생한다.
- onchange: occurs when the content of a form element, the selection, or the checked state have changed (for \<input>, \<keygen>, \<select>, and \<textarea>)
  - form element, selection, checked state의 내용이 변경될 때 발생한다.
  - (\<input>, \<keygen>, \<select>, \<textarea>의 경우)
- onmouseover: occurs when the pointer is moved onto an element, or onto one of its children
  - 포인터가 element 위로 이동하거나, children 중 하나 위로 이동할 때 발생한다.
- onmouseout: occurs when a user moves the mouse pointer out of an element, or out of one of its children
  - 사용자가 마우스 포인터를 element 밖으로 이동하거나, 해당 element 중 하나에서 벗어났을 때 발생한다.
- onmousedown: occurs when the user presses a mouse button over an element
  - 사용자가 element 위에서 마우스 버튼을 누를 때 발생한다.
- onmouseup: occurs when a user releases a mouse button over an element
  - 사용자가 element 위에서 마우스 버튼을 놓을 때 발생한다.
- onblur: occurs when an element loses focus
  - element가 focus를 잃을 때 발생한다.
- onfocus: occurs when an element gets focus
  - element가 focus를 얻을 때 발생한다.

<br>

> Corresponding events can be added to HTML elements as attributes.
>
> HTML element에 해당 이벤트를 속성으로 추가할 수 있다.

> 예: \<p onclick="someFunc()">some text\</p>

------

<br>

## Handling Events

###### 이벤트 핸들링

<br>

- Let's display an alert popup when the user clicks a specified button:
  - 사용자가 지정된 버튼을 클릭할 때 alert popup을 표시해보자.

```html
<button onclick="show()">
   Click Me
</button>

<script>
   function show() {
      alert("Hi there");
   }
</script>
```

[코드 실행 확인](https://code.sololearn.com/962/#js)

<br>

- Event handlers can be assigned to elements.
  - 이벤트 핸들러를 element에 할당할 수 있다.

```html
<button id="demo">
   Click Me
</button>

<script>
   var x = document.getElementById("demo");
   x.onclick = function() {
      document.body.innerHTML = Date();
   }
</script>
```

[코드 실행 확인](https://code.sololearn.com/963/#js)

<br>

> You can attach events to almost all HTML elements.
>
> 거의 모든 HTML element에 이벤트를 첨부할 수 있다.

------

<br>

## Events

###### 이벤트

<br>

- The `onload` and `onunload` events are triggered when the user enters or leaves the page.
  - `onload`와 `onunload` 이벤트는 사용자가 페이지에 들어가거나 떠날 때 trigger 된다.
- These can be useful when performing actions after the page is loaded.
  - 이는 페이지가 로딩된 후 action을 수행할 때 유용할 수 있다.

```html
<body onload="doSomething()">
   
</body>
```

<br>

- Similarly, the `window.onload` event can be used to run code after the whole page is loaded.
  - 마찬가지로, `window.onload` 이벤트는 전체 페이지가 로딩된 후 코드를 실행하는 데 사용될 수 있다.

```js
window.onload = function() {
   // some code
}
```

<br>

- The `onchange` event is mostly used on textboxes.
  - `onchange` 이벤트는 주로 textbox에서 사용된다.
- The event handler gets called when the text inside the textbox changes and focus is lost from the element.
  - 이벤트 핸들러는 textbox 내의 text가 변경되거나 element에서 focus를 잃을 때 호출된다.

```html
<input type="text" id="name" onchange="change()">

<script>
   function change() {
      var x = document.getElementById("name");
      x.value = x.value.toUpperCase();
   }
</script>
```

[코드 실행 확인](https://code.sololearn.com/964/#js)

<br>

> It's important to understand events, because they are an essential part of dynamic web pages.
>
> 동적 웹 페이지의 필수적인 부분이므로, 이벤트를 이해하는 것은 중요하다.

------

<br>

## Event Listeners

###### 이벤트 리스너

<br>

- The `addEventListener()` method attaches an event handler to an element without overwriting existing event handlers.
  - `addEventListener()` 메소드는 기존 이벤트 핸들러를 덮어쓰지 않고 element에 이벤트 핸들러를 첨부한다.
- You can add *many* event handlers to one element.
  - 하나의 element에 *많은* 이벤트 핸들러를 추가할 수 있다.
- You can also add many event handlers of the same type to one element, i.e., two "click" events.
  - 하나의 element, 즉 두 번의 "click" 이벤트에 동일한 type의 이벤트 핸들러를 추가할 수도 있다.

```js
element.addEventListener(event, function, useCapture);
```

<br>

- The first parameter is the event's `type` (like "click" or "mousedown").
  - 첫 번째 매개변수는 이벤트의 `type`이다.
  - ("click" 또는 "mousedown")
- The second parameter is the `function` we want to call when the event occurs.
  - 두 번째 매개변수는 이벤트가 발생할 때 호출할 `함수`이다.
- The third parameter is a Boolean value specifying whether to use event `bubbling` or event `capturing`.
  - 세 번째 매개변수는 이벤트 `bubbling` 또는 `capturing`을 사용할지 여부를 지정하는 Boolean 값이다.
- This parameter is optional.
  - 이 매개변수는 선택적이다.

<br>

> Note that you don't use the `"on"` prefix for this event; use `"click"` instead of `"onclick"`.
>
> 이 이벤트에는 `"on"` 접두어를 사용하지 않는다.
>
> `"onclick"` 대신 `"click"`을 사용한다.

<br>

- Example:

```js
element.addEventListener("click", myFunction);
element.addEventListener("mouseover", myFunction);

function myFunction() {
   alert("Hello World!");
}
```

<br>

- This adds two event listeners to the element.
  - 이는 element에 두 개의 이벤트 리스너를 추가한다.
- We can remove one of the listeners:
  - 리스너 중 하나를 제거할 수 있다.

```js
element.removeEventListener("mouseover", myFunction);
```

<br>

- Let's create an event handler that removes itself after being executed:
  - 실행 후 자체를 제거하는 이벤트 핸들러를 생성해보자.

```html
<button id="demo">
   Start
</button>

<script>
   var btn = document.getElementById("demo");
   btn.addEventListener("click", myFunction);
   
   function myFunction() {
      alert(Math.random());
      btn.removeEventListener("click", myFunction);
   }
</script>
```

[코드 실행 확인](https://code.sololearn.com/965/#js)

<br>

- After clicking the button, an alert with a random number displays and the event listener is removed.
  - 버튼을 클릭하면 난수(random number) alert가 표시되고, 이벤트 리스너가 제거된다.

<br>

> Internet Explorer version 8 and lower do not support the `addEventListener()` and `removeEventListener()` methods.
>
> IE 버전 8 이하는 `addEventListener()`와 `removeEventListener()` 메소드를 지원하지 않는다.

> However, you can use the document.`attachEvent()` method to attach event handlers in Internet Explorer.
>
> 하지만 document.`attachEvent()` 메소드를 사용해 IE에서 이벤트 핸들러를 첨부할 수 있다.

------

<br>

## QUIZ

- The type of function that executes when an event occurs is called:
  - 이벤트가 발생할 때 실행되는 함수의 type을 ...라고 한다.

> `event handler`

<br>

- Fill in the blanks to call func() when the button is clicked.
  - 버튼을 클릭할 때 func()를 호출해라.

```html
<button onclick="func()">
   Click Here
</button>
```

<br>

- Drag and drop from the options below to call the clear() function after body is loaded.
  - body가 로딩된 후 clear() 함수를 호출해라.

```html
<body onload="clear()">
   
</body>
```

<br>

- Can multiple event handlers be added to a single element?
  - 하나의 element에 여러 이벤트 핸들러를 추가할 수 있는가?

> `Yes`

<br>