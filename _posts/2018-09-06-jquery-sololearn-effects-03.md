---
layout: post
title: "(Effects 03) Drop-Down Menu 만들기"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## Drop-Down Menu

- Let's create a simple drop-down menu that will open upon clicking on the menu item.
  - menu의 item을 클릭하면 열리는 drop-down menu를 생성해보자.

<br>

- HTML:

```html
<div class="menu">
   <div id="item">Drop-Down</div>
   <div id="submenu">
      <a href="#">Link 1</a>
      <a href="#">Link 2</a>
      <a href="#">Link 3</a>
   </div>
</div>
```

<br>

- JS:

```js
$("#item").click(function() {
   $("#submenu").slideToggle(500);
});
```

[코드 실행 확인](https://code.sololearn.com/1143/#js)

<br>

- The code above handles the click event of the id="item" element and opens/closes the submenu in 500 milliseconds.
  - 위 코드는 id="item" element의 click 이벤트를 처리하고, 500 밀리초 동안 submenu를 열고 닫는다.

------

<br>

## QUIZ

- Fill in the blanks to hide the element in 1.5 seconds.
  - element를 1.5초로 hide 해라.

```js
$("p").hide(1500);
```

<br>