---
layout: post
title: "(DOM & Events 10) Module 7 Quiz"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## QUIZ

- Fill in the blanks to change the content of all paragraph tags of the page to "SoloLearn".
  - 페이지의 모든 p 태그 내용을 "SoloLearn"으로 변경해라.

```js
var arr = document.getElementsByTagName("p");

for (let i = 0; i < arr.length; i++) {
   arr[i].innerHTML = "SoloLearn";
}
```

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```html
<div id="test">
   <p>some text</p>
</div>

<script>
   var el = document.getElementById("test");
   alert(el.hasChildNodes());
</script>
```

> `true`

<br>

- Drag and drop from the options below to change the color of the paragraph with id="p2" to red.
  - id="p2" p의 color를 red로 변경해라.

```html
<script>
   var d = document.getElementById("p2");
   d.style.color = "red";
</script>
```

<br>

- Can you handle multiple events on the same HTML element?
  - 동일한 HTML element에서 여러 이벤트를 처리할 수 있는가?

> `Yes`

<br>

- Fill in the blanks to alert a message when the button is clicked.
  - 버튼을 클릭했을 때 message를 alert 해라.

```html
<button onclick="msg()">Click me</button>

<script>
   function msg() {
      alert("Ssup bro?");
   }
</script>
```

<br>

- Display an alert when the mouse pointer is over the div tag:
  - 마우스 포인터가 div 태그 위에 있을 때 alert 해라.

```html
<div onmouseover="alert('Ssup bro?')">
   put the mouse pointer over me
</div>
```

<br>