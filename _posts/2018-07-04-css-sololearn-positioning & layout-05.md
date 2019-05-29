---
layout: post
title: "(Positioning & Layout 05) clear 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS clear Property

###### clear 속성

------

<br>

<br>

## Clearing the Float

###### float 제거

<br>

- Elements that come after the floating element will flow around it.
  - floating element 뒤에 오는 element는 그 주위로 흐를 것이다.
- To avoid this, use the clear property.
  - 이를 방지하기 위해 clear 속성을 사용해라.
- The `clear` property specifies the sides of an element where other floating elements are not allowed to be.
  - `clear` 속성은 다른 floating element가 허용되지 않는 element의 면을 지정한다.

<br>

- In the example below, if we set the float property to the div, only the paragraph that comes after the div will be wrapped around the image.
  - 아래 예제에서 float 속성을 div로 설정하면, div 뒤에 오는 토막글만 이미지 주위를 둘러싼다.

<br>

- HTML:

```html
이 토막글은 div element 위에 있고, float right 속성의 영향을 받지 않는다.
<br /><br />
<div class="floating">
   <img src="css_logo.png" />
</div>
이 토막글은 div element 뒤에 오고, float right 속성의 영향을 받는다.
<br /><br />
이 토막글은 div element 뒤에도 오고, float right 속성의 영향을 받는다.
<br /><br />
```

<br>

- CSS:

```css
.floating {
   float: right;
}
```

[코드 실행 확인](https://code.sololearn.com/572/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-positioning & layout-05-01.png)

------

<br>

## Using clear

###### clear 사용

<br>

- Use the values `right`, `left`, and `both` to specify the sides of an element where other floating elements are not allowed to be.
  - `right`, `left`, `both` 값을 사용해서 다른 floating element가 허용되지 않는 element의 면을 지정한다.

<br>

> The default value is `none`, which allows floating elements on both sides.
>
> 기본값은 `none`이며, 양쪽에 floating element를 허용한다.

------

<br>

## Clearing Floats

###### flost 제거

<br>

- `both` is used to clear floats coming from either direction.
  - `both`는 어느 방향에서든 float을 제거하기 위해 사용된다.

<br>

- HTML:

```html
이 토막글은 div element 위에 있고, float right 속성의 영향을 받지 않는다.
<br /><br />
<div class="floating">
   <img src="css_logo.png" />
</div>
이 토막글은 div element 뒤에 오고, float right 속성의 영향을 받는다.
<br /><br class="clearing" />
이 토막글은 floating group에서 제외되었고, float right 속성의 영향을 받지 않는다.
<br /><br />
```

<br>

- CSS:

```css
.floating {
   float: right;
}

.clearing {
   clear: both;
}
```

[코드 실행 확인](https://code.sololearn.com/573/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-positioning & layout-05-02.png)

------

<br>

## QUIZ

- If there is an element with a float property, which neighbor elements will be affected?
  - float 속성을 가진 element가 있을 경우, 어떤 인접 element가 영향을 받는가?

> `The ones coming after that element`
>
> 해당 element 뒤에 오는 것들

<br>

- The clear property accepts the values none, left, right and:
  - clear 속성은 none, left, right, ... 값을 허용한다.

> `both`

<br>

- The clear property is used to:
  - clear 속성은 다음 작업에 사용된다.

> `take the next element off the floating group`
>
> floating group에서 다음 element를 제외시킨다

<br>