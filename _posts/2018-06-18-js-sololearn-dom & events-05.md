---
layout: post
title: "(DOM & Events 05) 애니메이션 생성하기"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

## Animations

###### 애니메이션

<br>

- Now that we know how to select and change DOM elements, we can create a simple animation.
  - 이제 어떻게 DOM element를 선택하고 변경하는지 알았으므로, 간단한 애니메이션을 생성할 수 있다.
- Let's create a simple HTML page with a `box` element that will be animated using JS.
  - JS를 사용해서 `box` element로 애니메이션 되는 간단한 HTML 페이지를 생성해보자.

```html
<style>
   #container {
      width: 200px;
      height: 200px;
      background: green;
      position: relative;
   }
   
   #box {
      width: 50px;
      height: 50px;
      background: red;
      position: absolute;
   }
</style>

<div id="container">
   <div id="box">
      
   </div>
</div>
```

[코드 실행 확인](https://code.sololearn.com/961/#js)

<br>

- Our `box` element is inside a `container` element.
  - `box` element는 `container` element 내에 있다.
- Note the position attribute used for the elements: the container is `relative` and the box is `absolute`.
  - element에 사용된 position 속성에 주목하자.
  - container는 `relative`이고, box는 `absolute`이다.
- This will allow us to create the animation relative to the container.
  - 이렇게 하면 container를 기준으로 애니메이션을 생성할 수 있다.

![img](/assets/img/js-sololearn-dom & events-05-01.png)

<br>

- We will be animating the red box to make it move to the right side of the container.
  - 빨간 box를 container의 오른쪽으로 움직일 것이다.

<br>

> You need to be familiar with CSS to better understand the code provided.
>
> 제공된 코드를 더 잘 이해하려면, CSS에 익숙해야 한다.

<br>

<br>

- To create an animation, we need to change the properties of an element at small intervals of time.
  - 애니메이션을 생성하려면, 작은 시간 간격으로 element의 속성을 변경해야 한다.
- We can achieve this by using the `setInterval()` method, which allows us to create a timer and call a function to change properties repeatedly at defined intervals (in milliseconds).
  - `setInterval()` 메소드를 사용해서 타이머를 생성하고, 정의된 간격(밀리초)으로 속성을 반복적으로 변경하는 함수를 호출할 수 있다.

<br>

- For example:

```js
var t = setInterval(move, 500);
```

<br>

- This code creates a timer that calls a `move()` function every 500 milliseconds.
  - 이 코드는 500 밀리초마다 `move()` 함수를 호출하는 타이머를 생성한다.
- Now we need to define the `move()` function, that changes the position of the box.
  - 이제 box의 위치를 변경하는 `move()` 함수를 정의해야 한다.

```js
// 시작 위치
var pos = 0;

// box element
var box = document.getElementById("box");

function move() {
   pos += 1;
   box.style.left = pos + "px";
}
```

<br>

> The `move()` function increments the `left` property of the box element by one each time it is called.
>
> `move()` 함수는 box element의 `left` 속성을 호출할 때마다 1씩 증가시킨다.

<br>

<br>

- The following code defines a timer that calls the `move()` function every 10 milliseconds:
  - 다음 코드는 10 밀리초마다 `move()` 함수를 호출하는 타이머를 정의한다.

```js
var t = setInterval(move, 10);
```

<br>

- However, this makes our box move to the right forever.
  - 하지만 이는 box가 오른쪽으로 영원히 이동하게 한다.
- To stop the animation when the box reaches the end of the container, we add a simple check to the move() function and use the `clearInterval()` method to stop the timer.
  - box가 container의 끝에 도달했을 때 애니메이션을 멈추려면, move() 함수에 간단한 확인을 추가하고, `clearInterval()` 메소드를 사용해서 타이머를 중지한다.

```js
function move() {
   if (pos >= 150) {
      clearInterval(t);
   } else {
      pos += 1;
      box.style.left = pos + "px";
   }
}
```

<br>

- When the left attribute of the box reaches the value of 150, the box reaches the end of the container, based on a container width of 200 and a box width of 50.
  - container의 width는 200, box의 width는 50이므로, box의 left 속성 값이 150에 도달할 때 box는 container의 끝에 도달한다.

<br>

- The final code:

```js
var pos = 0;

// box element
var box = document.getElementById("box");
var t = setInterval(move, 10);

function move() {
   if (pos >= 150) {
      clearInterval(t);
   } else {
      pos += 1;
      box.style.left = pos + "px";
   }
}
```

[코드 실행 확인](https://code.sololearn.com/953/#js)

------

<br>

## QUIZ

- To create an animation relative to a container, the position attribute for the container should be set to:
  - container를 기준으로 애니메이션을 생성하려면, container의 position 속성을 다음과 같이 설정해야 한다.

> `relative`

<br>

- What is the interval for this timer?
  - 이 타이머의 간격은 얼마인가?

```js
var t = setInterval(func, 10000);
```

> `10 seconds(초)`

<br>

- Which function is used to stop a setInterval timer?
  - 어떤 함수가 setInterval 타이머를 정지시키는 데 사용되는가?

> `clearInterval`

<br>
