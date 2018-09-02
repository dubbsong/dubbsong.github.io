---
layout: post
title: "08. 이미지 슬라이더 생성하기 (DOM & Events)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript Creating an Image Slider

###### JavaScript 이미지 슬라이더 생성하기

------

<br>

<br>

## Image Slider

###### 이미지 슬라이더

<br>

- Now we can create a sample image slider project.
  - 이제 샘플 이미지 슬라이더 프로젝트를 생성할 수 있다.
- The images will be changed using "Next" and "Prev" buttons.
  - "Next"와 "Prev" 버튼을 사용해서 이미지를 변경시킨다.
- Now, let's create our HTML, which includes an image and the two navigation buttons:
  - 이제, 이미지와 두 개의 탐색 버튼을 포함하는 HTML을 작성해보자.

```html
<div>
   <button>Prev</button>
   <img id="slider" src="http://www.sololearn.com/uploads/slider/1.jpg"
        width="200px" height="100px" />
   <button>Next</button>
</div>
```

[코드 실행 확인 링크](https://code.sololearn.com/954/#html)

<br>

- Next, let's define our sample images in an array:
  - 다음으로, 샘플 이미지를 배열로 정의해보자.

```js
var images = [
   "http://www.sololearn.com/uploads/slider/1.jpg",
   "http://www.sololearn.com/uploads/slider/2.jpg",
   "http://www.sololearn.com/uploads/slider/3.jpg"
];
```

<br>

<br>

- Now we need to handle the Next and Prev button clicks and call the corresponding functions to change the image.
  - 이제 Next와 Prev 버튼 클릭을 처리하고, 해당 함수를 호출해서 이미지를 변경해야 한다.

<br>

- HTML:

```html
<div>
   <button onclick="prev()"> Prev </button>
   <img id="slider" src="http://www.sololearn.com/uploads/slider/1.jpg"
        width="200px" height="100px" />
   <button onclick="next()"> Next </button>
</div>
```

<br>

- JS:

```js
var images = [
   "http://www.sololearn.com/uploads/slider/1.jpg",
   "http://www.sololearn.com/uploads/slider/2.jpg",
   "http://www.sololearn.com/uploads/slider/3.jpg"
];

var num = 0;

function next() {
   var slider = document.getElementById("slider");
   num++;
   if (num >= images.length) {
      num = 0;
   }
   slider.src = images[num];
}

function prev() {
   var slider = document.getElementById("slider");
   num--;
   if (num < 0) {
      num = images.length - 1;
   }
   slider.src = images[num];
}
```

[코드 실행 확인 링크](https://code.sololearn.com/955/#js)

<br>

- The `num` variable holds the current image.
  - `num` 변수는 현재 이미지를 유지한다.
- The next and previous button clicks are handled by their corresponding functions, which change the source of the image to the next/previous image in the array.
  - next와 prev 버튼 클릭은 해당 함수에 의해 처리되며, 이미지 소스를 배열의 next/prev 이미지로 변경한다.

------

<br>

## QUIZ

- Fill in the blanks to define an array.
  - 배열을 정의해라.

```js
var arr = ['A', 'B', 'C'];
```

<br>

- What will be the content of the paragraph after the user clicks on it twice?
  - 사용자가 두 번 클릭한 후 p의 내용은 무엇이 되는가?

```html
<p id='txt' onclick='test();'>20</p>

<script>
   function test() {
      var x = document.getElementById('txt');
      var n = x.innerHTML;
      x.innerHTML = n/2;
   }
</script>
```

> `5`

<br>