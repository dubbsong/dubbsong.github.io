---
layout: post
title: "(HTML5 11) Drag & Drop API"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML5 Drag & Drop API

------

<br>

<br>

## Making Elements Draggable

###### Drag 가능한 element 생성

<br>

- The drag and drop feature lets you "grab" an object and drag it to a different location.
  - drag & drop 기능을 사용하면 객체를 "잡아서" 다른 위치로 끌고 갈 수 있다.
- To make an element draggable, just set the `draggable` attribute to true:
  - element를 drag 가능하게 하려면, `draggable` 속성을 true로 설정하면 된다.

```html
<img draggable="true" />
```

<br>

> Any HTML element can be draggable.
>
> 모든 HTML element를 drag 할 수 있다.

<br>

- The API for HTML5 drag and drop is event-based.
  - HTML5의 drag & drop API는 이벤트 기반이다.

```html
<!DOCTYPE HTML>
<html>
   <head>
      <script>
         function allowDrop(ev) {
            ev.preventDefault();
         }
         
         function drag(ev) {
            ev.dataTransfer.setData("text", ev.target.id);
         }
         
         function drop(ev) {
            ev.preventDefault();
            var data = ev.dataTransfer.getData("text");
            ev.target.appendChild(document.getElementById(data));
         }
      </script>
   </head>
   <body>
      <div id="box" ondrop="drop(event)"
           ondragover="allowDrop(event)"
           style="border:1px solid black; width:200px; height:200px"></div>
      
      <img id="image" src="sample.jpg" draggable="true"
           ondragstart="drag(event)" width="150" height="50" alt="" />
   </body>
</html>
```

<br>

#### What to Drag

- When the element is dragged, the `ondragstart` attribute calls a function, drag(event), which specifies what data is to be dragged.
  - element가 drag 되면, `ondragstart` 속성은 drag 할 데이터를 지정하는 drag(event) 함수를 호출한다.
- The `dataTransfer.setData()` method sets the data type and the value of the dragged data:
  - `dataTransfer.setData()` 메소드는 데이터 type과 drag 된 데이터의 값을 설정한다.

```js
function drag(ev) {
   ev.dataTransfer.setData("text", ev.target.id);
}
```

<br>

- In our example, the data type is "text" and the value is the ID of the draggable element ("image").
  - 이 예제에서, 데이터 type은 "text"고, 값은 drag 가능한 element("image")의 ID이다.

<br>

#### Where to Drop

- The `ondragover` event specifies where the dragged data can be dropped.
  - `ondragover` 이벤트는 drag 된 데이터를 drop 할 수 있는 위치를 지정한다.
- By default, data and elements cannot be dropped in other elements.
  - 기본적으로, 데이터와 element는 다른 element에 drop 할 수 없다.
- To allow a drop, we must prevent the default handling of the element.
  - drop을 허용하려면, element의 기본 핸들링을 방지해야 한다.
- This is done by calling the event.`preventDefault()` method for the `ondragover` event.
  - 이것은 `ondragover` 이벤트에 대한 event.`preventDefault()` 메소드를 호출해서 수행된다.

<br>

#### Do the Drop

- When the dragged data is dropped, a drop event occurs.
  - drag 된 데이터가 drop 되면, drop 이벤트가 발생한다.
- In the example above, the `ondrop` attribute calls a function, drop(event):
  - 위 예제에서, `ondrop` 속성은 drop(event) 함수를 호출한다.

```js
function drop(ev) {
   ev.preventDefault();
   var data = ev.dataTransfer.getData("text");
   ev.target.appendChild(document.getElementById(data));
}
```

<br>

- The `preventDefault()` method prevents the browser's default handling of the data (default is open as link on drop).
  - `preventDefault()` 메소드는 브라우저의 기본 데이터 핸들링을 방지한다.
- The dragged data can be accessed with the `dataTransfer.getData()` method.
  - drag 된 데이터는 `dataTransfer.getData()` 메소드를 사용해서 액세스할 수 있다.
- This method will return any data that was set to the same type in the setData() method.
  - 이 메소드는 setData() 메소드에서 동일한 type으로 설정된 모든 데이터를 반환한다.
- The dragged data is the ID of the dragged element ("image").
  - drag 된 데이터는 drag 된 element("image")의 ID이다.

<br>

- At the end, the dragged element is appended into the drop element, using the appendChild() function.
  - 마지막에는, appendChild() 함수를 사용해서 drag 한 element를 drop element에 append 한다.

<br>

> Basic knowledge of JavaScript is required to understand and use the API.
>
> API를 이해하고 사용하려면 JavaScript에 대한 기본 지식이 필요하다.

------

<br>

## QUIZ

- How many times can HTML5 events be fired?
  - HTML5 이벤트는 몇 번이나 실행될 수 있는가?

> `Multiple`

<br>