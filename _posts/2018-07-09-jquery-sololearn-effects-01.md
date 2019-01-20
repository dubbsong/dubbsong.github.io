---
layout: post
title: "(Effects 01) toggle(), fadeToggle(), slideToggle() 메소드"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## Hide/Show

- jQuery has some easy-to-implement effects to create animations.
  - jQuery에는 애니메이션 생성을 위한 몇 가지 효과가 있다.
- The `hide()` and `show()` methods are used to hide and show the selected elements.
  - `hide()`와 `show()` 메소드는 선택한 element를 숨기거나 보여주는 데 사용된다.
- The `toggle()` method is used to toggle between hiding and showing elements.
  - `toggle()` 메소드는 hide/show element를 toggle 하는 데 사용된다.

```js
$(function() {
   $("p").click(function() {
      $("div").toggle();
   });
});
```

[코드 실행 확인](https://code.sololearn.com/1135/#js)

<br>

- The hide/show/toggle methods can take an optional argument, speed, which specifies the animation speed in `milliseconds`.
  - hide/show/toggle 메소드는 선택적 인수인 speed를 사용할 수 있다.
  - 이는 애니메이션 속도를 `밀리초` 단위로 지정한다.
- For example, let's pass 1000 millisecond as the speed argument to the toggle() method:
  - toggle() 메소드에 100 밀리초를 전달해보자.

```js
$(function() {
   $("p").click(function() {
      $("div").toggle(1000);
   });
});
```

[코드 실행 확인](https://code.sololearn.com/1136/#js)

<br>

> The hide/show/toggle methods can also take a second optional parameter `callback`, which is a function to be executed after the animation completes.
>
> hide/show/toggle 메소드는 두 번째 선택적 매개변수인 `callback`을 사용할 수도 있다.
>
> `callback`은 애니메이션이 완료된 후에 실행되는 함수다.

------

<br>

## Fade In/Out

- Similar to the hide/show methods, jQuery provides the `fadeIn/fadeOut` methods, which fade an element in and out of visibility.
  - hide/show 메소드와 마찬가지로, jQuery는 `fadeIn/fadeOut` 메소드를 제공한다.
  - 이는 element를 fade in/out 한다.
- Just like the `toggle()` method switches between hiding and showing, the `fadeToggle()` method fades in and out.
  - `toggle()` 메소드가 hide/show를 전환하는 것처럼, `fadeToggle()` 메소드는 fade in/out을 전환한다.

```js
$(function() {
   $("p").click(function() {
      $("div").fadeToggle(1000);
   });
});
```

[코드 실행 확인](https://code.sololearn.com/1137/#js)

<br>

- Just like toggle(), fadeToggle() takes two optional parameters: `speed` and `callback`.
  - toggle()과 마찬가지로, fadeToggle()은 `speed`와 `callback` 두 선택적 매개변수를 사용한다.

<br>

> Another method used for fading is `fadeTo()`, which allows fading to a given opacity (value between 0 and 1).
>
> fade에 사용되는 또 다른 메소드는 `fadeTo()`이다.
>
> 이는 주어진 opacity(0과 1 사이의 값)로 fade 한다.
>
> 예: `$("div").fadeTo(1500, 0.7);`

------

<br>

## Slide Up/Down

- The `slideUp()` and `slideDown()` methods are used to create a sliding effect on elements.
  - `slideUp()`과 `slideDown()` 메소드는 element에 sliding 효과를 생성하는 데 사용된다.
- Again, similar to the previous toggle methods, the `slideToggle()` method switches between the sliding effects and can take two optional parameters: speed and callback.
  - 이전의 toggle 메소드와 마찬가지로, `slideToggle()` 메소드는 sliding 효과를 전환하고, speed와 callback 두 선택적 매개변수를 사용할 수 있다.

```js
$(function() {
   $("p").click(function() {
      $("div").slideToggle(500);
   });
});
```

[코드 실행 확인](https://code.sololearn.com/1138/#js)

------

<br>

## QUIZ

- The speed parameter for the toggle() method is in:
  - toggle() 메소드의 speed 매개변수는 ...이다.

> `milliseconds`
>
> 밀리초

<br>

- Fill in the blanks to fade the paragraph to 60% opacity in 2 seconds.
  - p의 opacity를 60%, speed를 2초로 fade 해라.

```js
$("p").fadeTo(2000, 0.6);
```

<br>

- Fill in the blanks to slide down the div element in 3 seconds upon clicking on the paragraph.
  - p를 클릭했을 때 div element를 3초로 slide down 해라.

```js
$("p").click(function() {
   $("div").slideDown(3000);
});
```

<br>