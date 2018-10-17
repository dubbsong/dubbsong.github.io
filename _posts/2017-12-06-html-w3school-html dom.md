---
layout: post
title: HTML DOM 속성 & 메소드
categories: html
---

###### [w3schools](https://www.w3schools.com/) 참조

<br>

# HTML DOM Properties & Methods

###### HTML DOM 속성 & 메소드

------

<br>

<br>

## DOM Document

<br>

- `addEventListener()`: Attaches an event handler to the document
  - 문서에 이벤트 핸들러를 연결한다.

```html
<p>Click anywhere in the document. </p>

<p id='demo'></p>

<script>
   document.addEventListener('click', function() {
      document.getElementById('demo').innerHTML = 'Ssup bro?';
   });
</script>

<!-- 문서 내 아무 곳이나 클릭하면 id='demo' p에 Ssup bro?가 출력된다. -->
```

<br>

- `createTextNode()`: Creates a Text node
  - text node를 생성한다.

```html
<button onclick='myFunction()'>Click me</button>

<script>
   function myFunction() {
      var t = document.createTextNode('Ssup bro?');
      document.body.appendChild(t);
   }
</script>

<!-- 버튼을 클릭할 때마다 버튼 옆에 Ssup bro?가 생성된다. -->
```

<br>

- `getElementById()`: Returns the element that has the ID attribute with the specified value
  - 지정된 값으로 ID 속성을 가진 element를 반환한다.

```html
<p id='demo'>How are you?</p>

<button onclick='myFunction()'>Click me</button>

<script>
   function myFunction() {
      document.getElementById('demo').innerHTML = 'Ssup bro?';
   }
</script>

<!-- 버튼 클릭 시 How are you?가 Ssup bro?로 변경된다. -->
```

<br>

- `getElementsByClassName()`: Returns a NodeList containing all elements with the specified class name
  - 지정된 class name을 가진 모든 element를 포함하는 NodeList를 반환한다.

```html
<div class='example'>First div. </div>
<div class='example'>Second div. </div>

<button onclick='myFunction()'>Click me</button>

<script>
   function myFunction() {
      var getClass = document.getElementsByClassName('example');
      getClass[0].innerHTML = 'Ssup bro?';
   }
</script>

<!-- 버튼 클릭 시 First div.가 Ssup bro?로 변경된다. -->
```

<br>

- `getElementsByName()`: Returns a NodeList containing all elements with a specified name
  - 지정된 name을 가진 모든 element를 포함하는 NodeList를 반환한다.

```html
First Name: <input name='fname' type='text' value='Sam'><br>
First Name: <input name='fname' type='text' value='Leo'>

<button onclick='myFunction()'>Click me</button>

<p id='demo'></p>

<script>
   function myFunction() {
      var getName = document.getElementsByName('fname')[0].tagName;
      document.getElementById('demo').innerHTML = getName;
   }
</script>

<!--
INPUT
-->
<!-- 버튼 클릭 시 tagName인 INPUT이 출력된다. -->
```

<br>

- `getElementsByTagName()`: Returns a NodeList containing all elements with the specified tag name
  - 지정된 tag name을 가진 모든 element를 포함하는 NodeList를 반환한다.

```html
<button onclick='myFunction()'>Click me</button>

<ul>
   <li>HTML</li>
   <li>CSS</li>
   <li>JavaScript</li>
</ul>

<p id='demo'></p>

<script>
   function myFunction() {
      var getList = document.getElementsByTagName('li');
      document.getElementById('demo').innerHTML = getList[2].innerHTML;
   }
</script>

<!-- 버튼 클릭 시 JavaScript가 출력된다. -->
```

<br>

- `open()`: Opens an HTML output stream to collect output from document.write()
  - document.write()로부터 출력을 수집하기 위해 HTML 출력 stream을 연다.

```html
<button onclick='myFunction()'>Click me</button>

<script>
   function myFunction() {
      document.open();
      document.write('<h1>ssup</h1>');
      document.close();
   }
</script>

<!-- 버튼을 클릭하면 버튼이 사라지고 ssup이 생성된다. -->
```

<br>

- `querySelector()`: Returns the first element that matches a specified CSS selector(s) in the document
  - element의 지정된 CSS selector와 일치하는 첫 번째 child element를 반환한다.

```html
<h2 class='example'>How are you?</h2>
<p class='example'>All good?</p>

<button onclick='myFunction()'>Click me</button>

<script>
   function myFunction() {
      document.querySelector('.example').style.backgroundColor = '#20a19c';
   }
</script>

<!-- How are you?에 #20a19c 배경색이 입혀진다. -->
```

<br>

- `querySelectorAll()`: Returns a static NodeList containing all elements that matches a specified CSS selector(s) in the document
  - 문서에 지정된 CSS selector와 일치하는 모든 element를 포함하는 정적 NodeList를 반환한다.

```html
<h2 class='example'>How are you?</h2>
<p class='example'>All good?</p>

<button onclick='myFunction()'>Click me</button>

<script>
   function myFunction() {
      var x = document.querySelectorAll('.example');
      x[0].style.backgroundColor = '#998ac5';
   }
</script>

<!-- How are you?에 #998ac5 배경색이 입혀진다. -->
```

<br>

- `removeEventListener()`: Removes an event handler from the document (that has been attached with the `addEventListener()` method)
  - 문서에서 이벤트 핸들러를 제거한다.
  - (`addEventListener()` 메소드로 연결된다)

```html
<p>Click the button to remove the event handler. </p>

<button onclick='removeHandler()'>Click me</button>

<p id='demo'></p>

<script>
   document.addEventListener('mousemove', myFunction);
   
   function myFunction() {
      document.getElementById('demo').innerHTML = Math.random();
   }
   
   function removeHandler() {
      document.removeEventHandler('mousemove', myFunction);
   }
</script>

<!-- 마우스를 움직이면, 아래에 랜덤 숫자가 나타난다. -->
<!-- 버튼 클릭 시 mousemove 이벤트가 제거된다. -->
```

------

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
      var createList = document.createElement('li');
      var createText = document.createTextNode('JavaScript');
      createList.appendChild(createText);
      console.log(createList.appendChild(createText));	// "JavaScript"
      document.getElementById('myList').appendChild(createList);
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

- ##### `classList`: Returns the class name(s) of an element

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
<button onclick='myFunction()'>Click me</button>

<!-- 닫는 UL element 앞에 공백이 있으면, 결과가 "undefined"가 된다. -->
<ul id='myList'>
   <li>HTML</li>
   <li>CSS</li>
   <li>JavaScript</li></ul>

<p id='demo'></p>

<script>
   function myFunction() {
      var x = document.getElementById('myList').lastChild.innerHTML;
      document.getElementById('demo').innerHTML = x;
   }
</script>

<!-- 버튼 클릭 시 마지막 list인 JavaScript가 출력된다. -->
```

<br>

- `lastElementChild`: Returns the last child element of an element
  - element의 마지막 child element를 반환한다.

```html
<button onclick='myFunction()'>Click me</button>

<ul id='myList'>
   <li>HTML</li>
   <li>CSS</li>
   <li>JavaScript</li>
</ul>

<p id='demo'></p>

<script>
   function myFunction() {
      var x = document.getElementById('myList').lastElementChild.innerHTML;
      document.getElementById('demo').innerHTML = x;
   }
</script>

<!-- 버튼 클릭 시 마지막 list인 JavaScript가 출력된다. -->
```

<br>

- `querySelector()`: Returns the first child element that matches a specified CSS selector(s) of an element
  - element의 지정된 CSS selector와 일치하는 첫 번째 child element를 반환한다.

```html
<button onclick='myFunction()'>Click me</button>

<div id='myDIV'>
   <h2 class='example'>How are you?</h2>
   <p class='example'>All good?</p>
</div>

<script>
   function myFunction() {
      var x = document.getElementById('myDIV');
      x.querySelector('.example').innerHTML = 'Ssup bro?';
   }
</script>

<!-- 버튼 클릭 시 How are you?가 Ssup bro?로 변경된다. -->
<!-- 일치하는 첫 번째 child element를 변경한다. -->
```

<br>

- `querySelectorAll()`: Returns all child elements that matches a specified CSS selector(s) of an element
  - element의 지정된 CSS selector와 일치하는 모든 child element를 반환한다.

```html
<button onclick='myFunction()'>Click me</button>

<div id='myDIV'>
   <h2 class='example'>How are you?</h2>
   <p class='example'>All good?</p>
</div>

<script>
   function myFunction() {
      var x = document.getElementById('myDIV').querySelectorAll('.example');
      x[0].style.backgroundColor = '#20a19c';
   }
</script>

<!-- 버튼 클릭 시 How are you? 배경색이 #20a19c로 변경된다. -->
<!-- 해당 elemet를 index로 지정해서 변경할 수 있다. -->
```

<br>

- `removeChild()`: Removes a child node from an element
  - element에서 child node를 제거한다.

```html
<button onclick='myFunction()'>Click me</button>

<ul id='myList'>
   <li>HTML</li>
   <li>CSS</li>
   <li>JavaScript</li>
</ul>

<script>
   function myFunction() {
      var getList = document.getElementById('myList');
      getList.removeChild(getList.children[0]);
   }
</script>

<!-- 버튼을 클릭할 때마다 첫 번째 list가 제거된다. -->
```

<br>

- `removeEventListener()`: Removes an event handler that has been attached with the addEventListener() method
  - addEventListener() 메소드로 첨부된 이벤트 핸들러를 제거한다.

```html
<div id='myDIV' style='background-color:#20a19c;padding:40px'>
   <button onclick='removeHandler()'>Click me</button>
</div>

<p id='demo'></p>

<script>
   document.getElementById('myDIV').addEventListener('mousemove', myFunction);
   
   function myFunction() {
      document.getElementById('demo').innerHTML = Math.random();
   }
   
   function removeHandler() {
      document.getElementById('myDIV').removeEventListener('mousemove', myFunction);
   }
</script>

<!-- div 내에서 마우스를 움직이면, 아래에 랜덤 숫자가 나타난다. -->
<!-- 버튼 클릭 시 mousemove 이벤트가 제거된다. -->
```

<br>

- `scrollHeight`: Returns the entire height of an element, including padding
  - padding을 포함한 element의 전체 높이를 반환한다.

```html
<head>
   <style>
      #myDIV {
         margin-top: 10px;
         width: 200px;
         height: 200px;
         background-color: #20a19c;
      }
      
      #content {
         padding: 20px;
         width: 300px;
         height: 300px;
         background-color: #998ac5;
         opacity: 0.4;
      }
   </style>
</head>

<body>
   <button onclick='myFunction()'>Click me</button>
   
   <p id='demo'></p>
   
   <div id='myDIV'>
      <div id='content'>ssup</div>
   </div>
   
   <script>
      function myFunction() {
         var getContent = document.getElementById('content');
         var x = getContent.scrollWidth;
         var y = getContent.scrollHeight;
         document.getElementById('demo').innerHTML = 'Width: ' + x + 'px<br>Height: ' + y + 'px';
      }
   </script>
</body>

<!--
Width: 340px
Height: 340px
-->
```

<br>

- `scrollTop`: Sets or returns the number of pixels an element's content is scrolled vertically
  - element의 content를 세로로 스크롤하는 픽셀 수를 설정하거나 반환한다.

```html
<head>
   <style>
      #myDIV {
         width: 200px;
         height: 200px;
         overflow: auto;
      }
      
      #content {
         width: 300px;
         height: 300px;
         background-color: #998ac5;
      }
   </style>
</head>

<body>
   <div id='myDIV' onscroll='myFunction()'>
      <div id='content'>ssup</div>
   </div>
   
   <p id='demo'></p>
   
   <script>
      function myFunction() {
         var getMyDiv = document.getElementById('myDIV');
         var x = getMyDiv.scrollLeft;
         var y = getMyDiv.scrollTop;
         document.getElementById('demo').innerHTML = 'Horizontally: ' + x + 'px<br>Vertically: ' + y + 'px';
      }
   </script>
</body>

<!-- 상하좌우 스크롤 시 아래에 x와 y 값이 표시된다. -->
```

------

<br>