---
layout: post
title: "03. 드롭다운 메뉴 만들기 (Effects)"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

# jQuery: Creating a Drop-Down Menu

###### 드롭다운 메뉴 만들기

------

<br>

<br>

## Drop-Down Menu

###### 드롭다운 메뉴

<br>

- Let's create a simple drop-down menu that will open upon clicking on the menu item.
  - 메뉴 항목을 클릭하면 열리는 간단한 드롭다운 메뉴를 만들어보자.

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

[코드 실행 확인 링크](https://code.sololearn.com/1143/#js)

<br>

- The code above handles the click event of the id="item" element and opens/closes the submenu in 500 milliseconds.
  - 위의 코드는 id="item" element의 click 이벤트를 처리하고, 500 milliseconds 안에 하위 메뉴를 열고 닫는다.

------

<br>

## QUIZ

- Fill in the blanks to hide the element in 1.5 seconds.
  - element를 1.5초 안에 숨겨라.

```js
$("p").hide(1500);
```

<br>