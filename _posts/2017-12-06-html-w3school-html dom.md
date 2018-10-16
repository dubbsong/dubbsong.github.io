---
layout: post
title: HTML DOM
categories: html
---

###### [w3schools](https://www.w3schools.com/) 참조

<br>

# HTML DOM

------

<br>

<br>

## DOM Element

<br>

- `addEventListener()`: Attaches an event handler to the specified element
  - 지정된 element에 이벤트 핸들러를 연결한다.

```html
<button id='myBtn'>Click me</button>

<p id='demo'></p>

<script>
   var btn = document.getElementById('myBtn');
   btn.addEventListener('click', function() {
      document.getElementById('demo').innerHTML = 'Hello World';
   });
</script>

<!-- 버튼 클릭 시 id='demo' p에 Hello World가 나타난다. -->
```

<br>

- `appendChild()`: Adds a new child node, to an element, as the last child node
  - 새 child node를 마지막 child node로 element에 추가한다.

```html
<button onclick='myFunction()'>Click me</button>

<ul id='myList'>
   <li>HTML</li>
   <li>CSS</li>
</ul>

<script>
   function myFunction() {
      var create_list = document.createElement('li');
      var create_text = document.createTextNode('JavaScript');
      create_list.appendChild(create_text);
      console.log(create_list.appendChild(create_text));	// "JavaScript"
      document.getElementById('myList').appendChild(create_list);
   }
</script>

<!-- 버튼을 클릭할 때마다 CSS list 아래로 JavaScript list가 생성된다. -->
```

<br>

- `childNodes`: Returns a collection of an element's child nodes (including text and comment nodes)
  - element의 child node(text node와 comment node 포함)의 collection을 반환한다.

```html
<button onclick='myFunction()'>Click me</button>

<p id='demo'></p>

<script>
   function myFunction() {
      var body_child_nodes = document.body.childNodes;
      console.log(body_child_nodes);
      // ► NodeList(7) [text, button, text, p#demo, text, script, text]
      var txt = '';
      
      for (let i = 0; i < body_child_nodes.length; i++) {
         txt = txt + body_child_nodes[i].nodeName + '<br>';
      }
      document.getElementById('demo').innerHTML = txt;
   }
</script>

<!--
#text
BUTTON
#text
P
#text
SCRIPT
#text
-->
```

<br>

- `children`: Returns a collection of an element's child element (excluding text and comment nodes)
  - element의 child element(text node와 comment node 제외)의 collection을 반환한다.

```html
<button onclick='myFunction()'>Click me</button>

<p id='demo'></p>

<script>
   function myFunction() {
      var body_children = document.body.children;
      console.log(body_children);
      // ► HTMLCollection(3) [button, p#demo, script, demo: p#demo]
      var txt = '';
      
      for (let i = 0; i < body_children.length; i++) {
         txt = txt + body_children[i].tagName + '<br>';
      }
      document.getElementById('demo').innerHTML = txt;
   }
</script>

<!--
BUTTON
P
SCRIPT
-->
```

<br>

- `classList`: Returns the class name(s) of an element
  - element의 class name을 반환한다.

```html
<head>
   <style>
      .my_style {
         font-size: 20px;
         text-align: center;
         width: 200px;
         height: 30px;
         background-color: #20a19c;
         color: #fff;
      }
   </style>
</head>

<body>
   <button onclick='myFunction()'>Click me</button>
   
   <div id='myDIV'>ssup</div>
   
   <script>
      function myFunction() {
         document.getElementById('myDIV').classList.add('my_style');
      }
   </script>
</body>

<!-- 버튼 클릭 시 기존 id='myDIV'에 my_style CSS를 적용시킨다. -->
```

<br>

- `className`: Sets or returns the value of the class attribute of an element
  - element의 class 속성 값을 설정하거나 반환한다.

```html
<head>
   <style>
      .my_style {
         font-size: 20px;
         text-align: center;
         width: 200px;
         height: 30px;
         background-color: #20a19c;
         color: #fff;
      }
   </style>
</head>

<body>
   <button onclick='myFunction()'>Click me</button>
   
   <div id='myDIV'>ssup</div>
   
   <script>
      function myFunction() {
         document.getElementById('myDIV').className = 'my_style';
      }
   </script>
</body>

<!-- 버튼 클릭 시 기존 id='myDIV'에 my_style CSS를 적용시킨다. -->
```

<br>

- `focus()`: Gives focus to an element
  - element에 focus를 준다.

```html
<head>
   <style>
      a {
         font-size: 20px;
      }
      
      a:focus, a:active {
         color: #20a19c;
      }
   </style>
</head>

<body>
   <a id='myAnchor' href='https://dubbsong.github.io/'>ssup</a>
   
   <input type='button' onclick='getFocus()' value='Get focus'>
   <input type='button' onclick='loseFocus()' value='Lose focus'>
   
   <script>
      function getFocus() {
         document.getElementById('myAnchor').focus();
      }
      
      function loseFocus() {
         document.getElementById('myAnchor').blur();
      }
   </script>
</body>

<!-- 각 버튼을 클릭 시 a text의 focus가 변경된다. -->
```

<br>

- `getElementsByClassName()`: Returns a collection of all child elements with the specified class name
  - 지정된 class name을 가지는 모든 child element의 collection을 반환한다.

```html
<button onclick='myFunction()'>Click me</button>

<ul class='myList'>
   <li class='child'>HTML</li>
   <li class='child'>CSS</li>
   <li class='child'>JavaScript</li>
</ul>

<script>
   function myFunction() {
      var getClassName = document.getElementsByClassName('myList')[0];
      getClassName.getElementsByClassName('child')[2].innerHTML = 'Vue.js';
   }
</script>

<!-- 버튼 클릭 시 JavaScript가 Vue.js로 변경된다. -->
```

<br>

- `getElementsByTagName()`: Returns a collection of all child elements with the specified tag name
  - 지정된 tag name을 가진 모든 child element의 collection을 반환한다.

```html
<button onclick='myFunction()'>Click me</button>

<ul>
   <li>HTML</li>
   <li>CSS</li>
   <li>JavaScript</li>
</ul>

<script>
   function myFunction() {
      var getTagName = document.getElementsByTagName('ul')[0];
      getTagName.getElementsByTagName('li')[2].innerHTML = 'Vue.js';
   }
</script>

<!-- 버튼 클릭 시 JavaScript가 Vue.js로 변경된다. -->
```

<br>

- `innerHTML`: Sets or returns the content of an element
  - element의 content를 설정하거나 반환한다.

```html
<p id='demo' onclick='myFunction()'>Click me</p>

<script>
   function myFunction() {
      document.getElementById('demo').innerHTML = 'Ssup bro?';
   }
</script>

<!-- text 클릭 시 Ssup bro?로 변경된다. -->
```

<br>

- `innerText`: Sets or returns the text content of a node and its descendants
  - node와 node 자손의 text content를 설정하거나 반환한다.

```html
<button onclick='myFunction()' id='myBtn'>Click me</button>

<p id='demo'></p>

<script>
   function myFunction() {
      var x = document.getElementById('myBtn').innerText;
      document.getElementById('demo').innerHTML = x;
   }
</script>

<!-- 버튼 클릭 시 버튼의 content가 그대로 출력된다. -->
```

<br>

- `lastChild`: Returns the last child node of an element
  - element의 마지막 child node를 반환한다.

```html

```

<br>

- 























