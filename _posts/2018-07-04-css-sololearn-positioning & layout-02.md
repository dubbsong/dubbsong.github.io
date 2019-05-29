---
layout: post
title: "(Positioning & Layout 02) visibility 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS visibility Property

###### visibility 속성

<br>

- The `visibility` property specifies whether an element is visible or hidden.
  - `visibility` 속성은 element를 표시할지 또는 숨길지를 지정한다.
- The most common values are `visible` and `hidden`.
  - 가장 일반적인 값은 `visible`과 `hidden`이다.

<br>

- Hiding an element can be done by setting the display property to "none" or the visibility property to "hidden".
  - element를 숨기는 것은 display 속성을 "none"으로 설정하거나, visibility 속성을 "hidden"으로 설정해서 수행할 수 있다.
- However, notice that these two methods produce different results:
  - 하지만, 이 두 가지 메소드는 다른 결과를 생성한다.
- `visibility: hidden` hides an element, but it will still take up the same space as before.
  - `visibility: hidden`은 element를 숨기지만, 이전과 동일한 공간을 차지한다.
- The element will be hidden, but it will still affect the layout:
  - element는 숨겨지지만, 여전히 layout에 영향을 미친다.

<br>

- HTML:

```html
<h1>This is a heading </h1>
<div class="hidden">
   This text will not display in browser.
</div>
<p>
   The space above this paragraph is empty because
   the visibility of the div element is set to hidden.
</p>
```

<br>

- CSS:

```css
div.hidden {
   visibility: hidden;
}
```

[코드 실행 확인](https://code.sololearn.com/565/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-positioning & layout-02-01.png)

<br>

- `display: none` hides an element, without holding a place for that element.
  - `display: none`은 해당 element에 대한 보관 장소 없이, element를 숨긴다.

<br>

- Changing `visibility: hidden;` to `display: none;` will produce the following result:
  - `visibility: hidden;`을 `display: none;`으로 변경하면 다음 결과가 생성된다.

```css
div.hidden {
   display: none;
}
```

[코드 실행 확인](https://code.sololearn.com/566/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-positioning & layout-02-02.png)

------

<br>

## QUIZ

- The values of the "visibility" property are:
  - "visibility" 속성의 값은 다음과 같다.

> [ ] `visible`
>
> [ ] show
>
> [ ] `hidden`
>
> [ ] inline

<br>