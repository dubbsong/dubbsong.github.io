---
layout: post
title: "(Events 03) To-Do List 만들기"
categories: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

# jQuery: Creating a To-Do List

###### To-Do List 만들기

<br>

- Let's create a To-Do list project using the concepts we have learned.
  - 배운 개념을 사용해서 To-Do list 프로젝트를 만들어보자.
- The To-Do list will be able to add new items to a list, as well as remove existing items.
  - To-Do list는 새 item을 list에 추가하고, 기존 item도 제거할 수 있다.

```html
<h1>My To-Do List</h1>
<input type="text" placeholder="New item" />
<button id="add">Add</button>
<ol id="mylist"></ol>
```

<br>

> Clicking the button should add the value of the input field to our \<ol> list.
>
> 버튼을 클릭하면 \<ol> list에 input field의 값을 추가해야 한다.

<br>

<br>

- Now, having the HTML ready, we can start writing our jQuery code.
  - 이제 HTML이 준비되면 jQuery 코드 작성을 시작할 수 있다.
- First, we handle the click event for the button:
  - 먼저, 버튼에 대한 클릭 이벤트를 처리한다.

```js
$(function() {
   $("#add").on("click", function() {
      // event handler
   });
});
```

<br>

- Inside the event handler we select the value of the input field and create a new \<li> element, adding it to the list:
  - 이벤트 핸들러 내에서 input field의 값을 선택하고, 새 \<li> element를 생성해서 list에 추가한다.

```js
var val = $("input").val();

if (val !== "") {
   var elem = $("<li></li>").text(val);
   $(elem).append("<button class='rem'>X</button>");
   $("#mylist").append(elem);
   $("input").val("");	// clear the input
}
```

<br>

- The code above takes the value of the input field, assigns it to the `val` variable.
  - 위 코드는 input field의 값을 가져와서, `val` 변수에 할당한다.
- The `if` statement checks that the value is not blank and then creates a new \<li> element.
  - `if` 문은 값이 비어 있지 않은지 확인한 다음, 새 \<li> element를 생성한다.
- A button for removing it is added, after which the newly created element is added to the \<ol id="mylist"> list.
  - 제거하기 위한 버튼이 추가된 후, 새로 생성된 element가 \<ol id="mylist"> list에 추가된다.

<br>

- Here's the complete code in action:
  - 다음은 동작하는 전체 코드이다.

```js
$(function() {
   $("#add").on("click", function() {
      var val = $("input").val();
      if (val !== "") {
         val elem = $("<li></li>").text(val);
         $(elem).append("<button class='rem'>X</button>");
         $("#mylist").append(elem);
         $("input").val("");
      }
   });
});
```

[코드 실행 확인](https://code.sololearn.com/1133/#js)

> The remove button is not working yet.
>
> 제거 버튼이 아직 작동하지 않는다.

<br>

<br>

- All that is left to do is handle the click event on the class="rem" button and remove the corresponding \<li> element from the list.
  - 해야 할 남은 일은, class="rem" 버튼에서 클릭 이벤트를 처리하고, 해당 \<li> element를 list에서 제거하는 것이다.

```js
$(".rem").on("click", function() {
   $(this).parent().remove();
});
```

<br>

- Remember, `this` is the current object.
  - `this`는 현재 객체라는 것을 기억해라.
- The code above removes the parent of the current object, which in our case is the parent of the remove button, the \<li> element.
  - 위 코드는 현재 객체의 parent(부모)를 제거한다.
  - 이 경우에는 제거 버튼의 parent(부모)인 \<li> element이다.

<br>

- The complete code:
  - 전체 코드:

```js
$(function() {
   $("#add").on("click", function() {
      var val = $("input").val();
      if (val !== "") {
         var elem = $("<li></li>").text(val);
         $(elem).append("<button class='rem'>X</button>");
         $("#mylist").append(elem);
         $("input").val("");
         $(".rem").on("click", function() {
            $(this).parent().remove();
         });
      }
   });
});
```

[코드 실행 확인](https://code.sololearn.com/1134/#js)

------

<br>

## QUIZ

- Fill in the blanks to create a new div element and add it to the element with id="test".
  - 새 div element를 만들고, id="test" element를 사용해서 div에 추가해라.

```js
var e = $("<div></div>");
$("#test").append(e);
```

<br>

- Which keyword represents the current object?
  - 현재 객체를 나타내는 키워드는 무엇인가?

> `this`

<br>