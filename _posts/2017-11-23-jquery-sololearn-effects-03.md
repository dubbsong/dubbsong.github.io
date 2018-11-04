---
layout: post
title: "(Effects 03) Drop-Down 메뉴"
categories: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

# jQuery Drop-Down Menu

###### Drop-Down 메뉴

<br>

- Let's create a simple drop-down menu that will open upon clicking on the menu item.
  - 메뉴 item을 클릭하면 열리는 간단한 drop-down 메뉴를 생성해보자.

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
$(function() {
   $("#item").click(function() {
      $("#submenu").slideToggle(500);
   });
});
```

[코드 실행 확인](https://code.sololearn.com/1143/#js)

<br>

- The code above handles the click event of the id="item" element and opens/closes the submenu in 500 milliseconds.
  - 위 코드는 id="item" element의 click 이벤트를 처리하고, 500 밀리초 내에 하위 메뉴를 열고 닫는다.

------

<br>

## QUIZ

- Fill in the blanks to hide the element in 1.5 seconds.
  - 1.5초 내에 element를 hide 해라.

```js
$("p").hide(1500);
```

<br>