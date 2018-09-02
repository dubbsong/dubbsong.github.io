---
layout: post
title: "07. 이벤트 전달하기 (DOM & Events)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript Event Propagation

###### JavaScript 이벤트 전달하기

<br>

- There are two ways of event propagation in the HTML DOM: `bubbling` and `capturing`.
  - HTML DOM에는 이벤트를 전달하는 `bubbling`과 `capturing`의 두 가지 방법이 있다.

<br>

- Event propagation allows for the definition of the element order when an event occurs.
  - 이벤트 전달은 이벤트가 발생할 때 element의 정의를 허용한다.
- If you have a \<p> element inside a \<div> element, and the user clicks on the \<p> element, which element's "click" event should be handled first?
  - \<div> element 내에 \<p> element가 있고, 사용자가 \<p> element를 클릭하면, 어떤 element의 "클릭" 이벤트가 먼저 처리되어야 하는가?

<br>

- In `bubbling`, the innermost element's event is handled first and then the outer element's event is handled.
  - `bubbling`에서는, 맨 안쪽 element의 이벤트가 먼저 처리된 다음, 바깥쪽 element의 이벤트가 처리된다.
- The \<p> element's click event is handled first, followed by the \<div> element's click event.
  - \<p> element의 클릭 이벤트가 먼저 처리되고, \<div> element의 클릭 이벤트가 처리된다.

<br>

- In `capturing`, the outermost element's event is handled first and then the inner.
  - `capturing`에서는, 가장 바깥쪽 element의 이벤트가 먼저 처리된 다음, 안쪽이 처리된다.
- The \<div> element's click event is handled first, followed by the \<p> element's click event.
  - \<div> element의 클릭 이벤트가 먼저 처리되고, \<p> element의 클릭 이벤트가 처리된다.

<br>

> Capturing goes `down` the DOM.
>
> capturing은 DOM을 따라 내려간다.

> Bubbling goes `up` the DOM.
>
> bubbling은 DOM을 따라 올라간다.

------

<br>

## Capturing vs. Bubbling

- The `addEventListener()` method allows you to specify the propagation type with the `"useCapture"` parameter.
  - `addEventListener()` 메소드를 사용하면, `"useCapture"` 매개변수를 사용해서 전달 타입을 지정할 수 있다.

```js
addEventListener(event, function, useCapture)
```

<br>

- The default value is `false`, which means the bubbling propagation is used; when the value is set to `true`, the event uses the capturing propagation.
  - 기본값은 `false`이며, 이는 bubbling 전달이 사용됨을 의미한다.
  - 값이 `true`로 설정되면, 이벤트는 capturing 전달을 사용한다.

```js
// capturing 전달
elem1.addEventListener("click", myFunction, true);

// bubbling 전달
elem2.addEventListener("click", myFunction, false);
```

<br>

> This is particularly useful when you have the same event handled for multiple elements in the DOM hierarchy.
>
> 이는 특히 DOM 계층의 여러 element에 대해 동일한 이벤트 처리가 될 때 유용하다.

------

<br>

## QUIZ

- A paragraph is inside a div element.
  - p는 div element 내에 있다.
- You want the paragraph's click event to be handled first.
  - p의 클릭 이벤트가 먼저 처리되기를 원한다.
- You should use:
  - 무엇을 사용해야 하는가?

> `bubbling`

<br>

- Drag and drop from the options below to handle the click event and use capturing propagation.
  - 클릭 이벤트를 처리하고, capturing 전달을 사용해라.

```js
x.addEventListener("click", func, true);
```

<br>