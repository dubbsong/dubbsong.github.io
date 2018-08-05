---
layout: post
title: "01. Hide/Show, Fade, Slide 메소드 (Effects)"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com) jQuery 번역

<br>

# Hide/Show, Fade, Slide 메소드

------

<br>

<br>

## Hide/Show

- jQuery has some easy-to-implement effects to create animations.
  - jQuery에는 애니메이션을 만들기 위한 몇 가지 쉬운 효과가 있다.
- The `hide()` and `show()` methods are used to hide and show the selected elements.
  - `hide()`와 `show()` 메소드는 선택한 element를 숨기거나 표시하는 데 사용된다.
- The `toggle()` method is used to toggle between hiding and showing elements.
  - `toggle()` 메소드는 숨기거나 표시하는 element를 토글하는 데 사용된다.

```js
$(function() {
   $("p").click(function() {
      $("div").toggle();
   });
});
```

[코드 실행 확인 링크](https://code.sololearn.com/1135/#js)

<br>

- The hide/show/toggle methods can take an optional argument, speed, which specifies the animation speed in `milliseconds`.
  - hide/show/toggle 메소드는 선택적 인수인 speed를 사용할 수 있다.
  - 이 인수는 애니메이션 속도를 `milliseconds`(1000분의 1초) 단위로 지정한다.
- For example, let's pass 1000 millisecond as the speed argument to the toggle() method:
  - 예를 들어, speed 인수로 1000 millisecond를 toggle() 메소드에 전달해보자.

```js
$(function() {
   $("p").click(function() {
      $("div").toggle(1000);
   });
});
```

[코드 실행 확인 링크](https://code.sololearn.com/1136/#js)

<br>

> The hide/show/toggle methods can also take a second optional parameter `callback`, which is a function to be executed after the animation completes.
>
> hide/show/toggle 메소드는 두 번째 선택적 매개변수 `callback`을 사용할 수도 있다.
>
> 이 callback은 애니메이션이 완료된 후에 실행되는 함수이다.

------

<br>

## Fade In/Out

- Similar to the hide/show methods, jQuery provides the `fadeIn/fadeOut` methods, which fade an element in and out of visibility.
  - hide/show 메소드와 마찬가지로, jQuery는 `fadeIn/fadeOut` 메소드를 제공한다.
  - 이 메소드는 가시성에 대해 element를 fade in/fade out 한다.
- Just like the `toggle()` method switches between hiding and showing, the `fadeToggle()` method fades in and out.
  - `toggle()` 메소드가 hiding과 showing 사이를 전환하는 것처럼, `fadeToggle()` 메소드는 fade in/fade out 한다.
- Let's see `fadeToggle()` in action:
  - `fadeToggle()`의 작동을 살펴보자.

```js
$(function() {
   $("p").click(function() {
      $("div").fadeToggle(1000);
   });
});
```

[코드 실행 확인 링크](https://code.sololearn.com/1137/#js)

<br>

- Just like toggle(), fadeToggle() takes two optional parameters: `speed` and `callback`.
  - toggle()과 마찬가지로, fadeToggle()은 `speed`와 `callback`이라는 두 가지 선택적 매개변수를 사용한다.

<br>

> Another method used for fading is `fadeTo()`, which allows fading to a given opacity (value between 0 and 1).
>
> fading에 사용되는 또 다른 방법은 `fadeTo()`이다.
>
> 이 방법은 주어진 불투명도(0과 1 사이의 값)로 fading을 할 수 있다.

> For example: $("div").fadeTo(1500, 0.7);

------

<br>

## Slide Up/Down

- The `slideUp()` and `slideDown()` methods are used to create a sliding effect on elements.
  - `slideUp()`과 `slideDown()` 메소드는 element에 sliding 효과를 만드는 데 사용된다.
- Again, similar to the previous toggle methods, the `slideToggle()` method switches between the sliding effects and can take two optional parameters: speed and callback.
  - 이전의 toggle 메소드와 마찬가지로, `slideToggle()` 메소드는 sliding 효과를 전환하고, 두 가지 선택적 매개변수인 speed와 callback을 사용할 수 있다.

<br>

- For example:

```js
$(function() {
   $("p").click(function() {
      $("div").slideToggle(500);
   });
});
```

[코드 실행 확인 링크](https://code.sololearn.com/1138/#js)

------

<br>

## QUIZ

- The speed parameter for the toggle() method is in:
  - toggle() 메소드의 speed 매개변수는 다음과 같다.

> [ ] `milliseconds`
>
> [ ] seconds
>
> [ ] minutes

<br>

- Fill in the blanks to fade the paragraph to 60% opacity in 2 seconds.
  - 2초 안에 p를 60% 불투명도로 fade 해라.

```js
$("p").fadeTo(2000, 0.6);
```

<br>

- Fill in the blanks to slide down the div element in 3 seconds upon clicking on the paragraph.
  - p를 클릭해서 3초 안에 div element를 아래로 slide 해라.

```js
$("p").click(function() {
   $("div").slideDown(3000);
});
```

<br>
