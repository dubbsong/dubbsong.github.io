---
layout: post
title: "(Effects 02) animate() 메소드"
categories: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

# jQuery: animate() Method

###### animate() 메소드

<br>

- The `animate()` method lets you animate to a set value, or to a value relative to the current value.
  - `animate()` 메소드를 사용하면 설정 값 또는 현재 값과 관련된 값에 애니메이션을 적용할 수 있다.
- You need to define the CSS properties to be animated as its parameter in `JSON` format (`"key":"value"` pairs).
  - `JSON` 형식(`"key":"value"` 쌍)의 매개변수로 애니메이션 되도록 CSS 속성을 정의해야 한다.
- The second parameter defines the speed of the animation.
  - 두 번째 매개변수는 애니메이션의 속도를 정의한다.
- For example, the following code animates the `width` property of the div in 1 second to the value 250px:
  - 예를 들어, 다음 코드는 div의 `width` 속성을 1초에 250px 값으로 애니메이션 한다.

```js
$("div").click(function() {
   $("div").animate({width:'250px'}, 1000);
});
```

[코드 실행 확인](https://code.sololearn.com/1139/#js)

<br>

- Note the `JSON` format for providing the CSS parameters.
  - CSS 매개변수를 제공하기 위한 `JSON` 형식에 주의해라.
- The `JSON` syntax was also used in the previous modules when manipulating CSS properties.
  - `JSON` 구문은 CSS 속성을 조작할 때 이전 모듈에서도 사용되었다.

<br>

> You can animate any CSS property using the above mentioned syntax, but there is one important thing to remember.
>
> 위에서 언급한 구문을 사용해서 CSS 속성을 애니메이션 할 수 있지만, 기억해야 할 중요한 게 하나 있다.

> All property names must be `camel-cased` when used with the animate() method (`camelCase` is the practice of writing compound words or phrases such that each word or abbreviation begins with a capital letter with the first word in lowercase).
>
> animate() 메소드와 함께 사용할 때, 모든 속성 이름을 `낙타 대문자`로 사용해야 한다.
>
> (`낙타 대문자`는 각 단어나 약어의 첫 글자가 소문자이고, 대문자로 시작하는 복합어나 구문을 작성하는 관행이다.)

> You will need to write `paddingLeft` instead of padding-left, `marginRight` instead of margin-right, and so on.
>
> padding-left 대신에 `paddingLeft`를, margin-right 대신에 `marginRight`로 작성해야 한다.

<br>

<br>

- Multiple properties can be animated at the same time by separating them with `commas`.
  - 여러 속성은 `쉼표`로 구분해서 동시에 애니메이션을 적용할 수 있다.

```js
$("div").animate({
   width: '250px',
   height: '250px'
}, 1000);
```

[코드 실행 확인](https://code.sololearn.com/1140/#js)

<br>

- It is also possible to define `relative` values (the value is then relative to the element's current value).
  - `상대적인` 값을 정의할 수도 있다.
  - (값은 element의 현재 값을 기준으로 한다.)
- This is done by putting `+=` or `-=` in front of the value:
  - 이는 `+=` 또는 `-=`를 값 앞에 놓음으로써 수행할 수 있다.

```js
$("div").animate({
   width: '+=250px',
   height: '+=250px'
}, 1000);
```

[코드 실행 확인](https://code.sololearn.com/1141/#js)

<br>

> To stop an animation before it is finished, jQuery provides the `stop()` method.
>
> 애니메이션이 끝나기 전에 애니메이션을 정지시키기 위해 jQuery는 `stop()` 메소드를 제공한다.

------

<br>

## Animation Queue

###### 애니메이션 queue

<br>

- By default, jQuery comes with queue functionality for animations.
  - 기본적으로 jQuery에는 애니메이션을 위한 queue 기능이 있다.
- This means that if you write multiple animate() calls one after another, jQuery creates an "internal" queue for these method calls.
  - 즉, 여러 animate() 호출을 차례로 작성하면, jQuery는 이러한 메소드 호출에 대한 "내부" queue를 생성한다.
- Then it runs the animate calls `one-by-one`.
  - 그런 다음 애니메이션 호출을 하나씩 실행한다.

<br>

- For example:

```js
var div = $("div");
div.animate({opacity: 1});
div.animate({height:'+=100px', width:'+=100px', top:'+=100px'}, 500);
div.animate({height:'-=100px', width:'-=100px', left:'+=100px'}, 500);
div.animate({height:'+=100px', width:'+=100px', top:'-=100px'}, 500);
div.animate({height:'-=100px', width:'-=100px', left:'-=100px'}, 500);
div.animate({opacity: 0.5});
```

[코드 실행 확인](https://code.sololearn.com/1142/#js)

<br>

- Each `animate()` method call will run one after another.
  - 각 `animate()` 메소드 호출은 차례로 실행된다.
- Remember, to manipulate the position of elements, you need to set the CSS position property of the element to `relative`, `fixed`, or `absolute`.
  - element의 위치를 조작하려면, element의 CSS position 속성을 `relative`, `fixed`, `absolute`로 설정해야 한다.

<br>

> The animate() method, just like the hide/show/fade/slide methods, can take an optional `callback` function as its parameter, which is executed after the current effect is finished.
>
> animate() 메소드는 hide/show/fade/slide 메소드와 마찬가지로, 선택적 `callback` 함수를 매개변수로 사용해서 현재 효과가 끝난 후에 실행될 수 있다.

------

<br>

## QUIZ

- Which of the following can be used with the animate() method?
  - animate() 메소드와 함께 사용할 수 있는 것은 무엇인가?

> [ ] padding-Left
>
> [ ] padding_left
>
> [ ] `paddingLeft`

<br>

- Fill in the blanks to animate the opacity and height properties of the div element in 5 seconds.
  - 5초 내에 div element의 opacity와 height 속성에 애니메이션을 적용해라.

```js
$("div").animate({
   opacity: 0.5,
   height: '+=100px'
}, 5000);
```

<br>

- By default, jQuery creates a queue for each animate() call.
  - 기본적으로, jQuery는 각 animate() 호출에 대한 queue를 생성한다.

> `True`

<br>