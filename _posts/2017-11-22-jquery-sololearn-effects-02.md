---
layout: post
title: "SoloLearn jQuery 번역 - 02. animate() (Effects)"
categories: dev
tags: jquery
---

## animate()

- The `animate()` method lets you animate to a set value, or to a value relative to the current value.
  - `animate()` 메소드를 사용하면 설정 값이나, 현재 값과 관련된 값에 애니메이션을 적용할 수 있다.
- You need to define the CSS properties to be animated as its parameter in `JSON` format (`"key":"value"` pairs).
  - `JSON` 형식(`"key":"value"` 쌍)의 매개변수로 애니메이션되도록 CSS 속성을 정의해야 한다.
  - `JSON`: a format for storing and transporting data
- The second parameter defines the speed of the animation.
  - 두 번째 매개변수는 애니메이션의 속도를 정의한다.
- For example, the following code animates the `width` property of the div in 1 second to the value 250px:
  - 예를 들어, 다음 코드는 div의 `width` 속성을 1초에 250px 값으로 애니메이션 한다.

```js
$("div").click(function() {
   $("div").animate({width: '250px'}, 1000);
});
```

[코드 실행 확인 링크](https://code.sololearn.com/1139/#js)

<br>

- Note that `JSON` format for providing the CSS parameters.
  - CSS 매개변수를 제공하기 위한 `JSON` 형식에 주의해라.
- The `JSON` syntax was also used in the previous modules when manipulating CSS properties.
  - CSS 속성을 조작할 때 `JSON` 구문도 이전 module에서 사용되었다.

<br>

> You can animate any CSS property using the above mentioned syntax, but there is one important thing to remember: all property names must be `camel-cased` when used with the animate() method.
>
> 위에서 언급한 구문을 사용해서 CSS 속성을 애니메이션으로 만들 수 있지만, 기억해야 할 중요한 게 하나 있다.
>
> animate() 메소드와 함게 사용할 때는 모든 속성 이름을 `camel-cased`로 사용해야 한다.

> You will need to write `paddingLeft` instead of padding-left, `marginRight` instead of margin-right, and so on.
>
> padding-left 대신 `paddingLeft`를, margin-right 대신 `marginRight`를 사용해야 한다.

------

<br>

## animate() 02

- Multiple properties can be animated at the same time by separating them with `commas`.
  - 여러 속성은 `쉼표`로 구분해서 동시에 애니메이션을 적용할 수 있다.

<br>

- For example:

```js
$("div").animate({
   width: '250px',
   height: '250px'
}, 1000);
```

[코드 실행 확인 링크](https://code.sololearn.com/1140/#js)

<br>

- It is also possible to define `relative` values (the value is then relative to the element's current value).
  - `relative` 값을 정의할 수도 있다.
  - (값은 element의 현재 값에 비례한다.)
- This is done by putting += or -= in front of the value:
  - 이것은 += 또는 -=을 값의 앞에 놓음으로써 가능하다.

```js
$("div").animate({
   width: '+=250px',
   height: '+=250px'
}, 1000);
```

[코드 실행 확인 링크](https://code.sololearn.com/1141/#js)

<br>

> To stop an animation before it is finished, jQuery provides the `stop()` method.
>
> 애니메이션이 끝나기 전에 정지시키기 위해, jQuery는 `stop()` 메소드를 제공한다.

------

<br>

## Animation Queue

- By default, jQuery comes with queue functionality for animations.
  - 기본적으로 jQuery는 애니메이션 queue 기능을 제공한다.
- This means that if you write multiple animate() calls one after another, jQuery creates an "internal" queue for these method calls.
  - 즉, 여러 개의 animate() 호출을 차례로 작성하면 jQuery는 메소드 호출에 대한 "internal" queue를 만든다.
- Then it runs the animate calls `one-by-one`.
  - 그런 다음 애니메이션 호출을 `하나하나씩` 실행한다.

<br>

- For example:

```js
var div = $("div");
div.animate({opacity: 1});
div.animate({height: '+=100px', width: '+=100px', top: '+=100px'}, 500);
div.animate({height: '-=100px', width: '-=100px', left: '+=100px'}, 500);
div.animate({height: '+=100px', width: '+=100px', top: '-=100px'}, 500);
div.animate({height: '-=100px', width: '-=100px', left: '-=100px'}, 500);
div.animate({opacity: 0.5});
```

[코드 실행 확인 링크](https://code.sololearn.com/1142/#js)

<br>

- Each `animate()` method call will run one after another.
  - 각 `animate()` 메소드 호출은 차례대로 실행된다.
- Remember, to manipulate the position of elements, you need to set the CSS position property of the element to `relative`, `fixed`, or `absolute`.
  - element의 위치를 조작하려면, element의 CSS 위치 속성을 `relative`, `fixed`, `absolute`로 설정해야 한다.

<br>

> The animate() method, just like the hide/show/fade/slide methods, can take an optional `callback` function as its parameter, which is executed after the current effect is finished.
>
> animate() 메소드는 hide/show/fade/slide 메소드와 마찬가지로, 선택적 `callback` 함수를 매개변수로 사용해서 현재 효과가 끝난 후 실행될 수 있다.

------

<br>

## QUIZ

- Which of the following can be used with the animate() method?
  - 다음 중 animate() 메소드와 함께 사용할 수 있는 것은 어떤 것인가?

> [ ] `paddingLeft`
>
> [ ] padding-Left
>
> [ ] padding_Left

<br>

- Fill in the blanks to animate the opacity and height properties of the div element in 5 seconds.
  - div element의 불투명도와 높이 속성에 5초 동안 애니메이션을 적용해라.

```js
$("div").animate({
   opacity: 0.5,
   height: '+=100px'
}, 5000);
```

<br>

- By default, jQuery creates a queue for each animate() call.
  - 기본적으로 jQuery는 각 animate() 호출에 대한 queue를 만든다.

> [ ] `True`
>
> [ ] False

<br>
