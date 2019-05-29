---
layout: post
title: "(Properties 12) 마우스 커서 커스터마이징"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS Customizing the Mouse Cursor

###### 마우스 cursor 커스터마이징

------

<br>

<br>

## Setting the Mouse Cursor Style

###### 마우스 cursor style 설정

<br>

- CSS allows you to set your desired cursor style when you mouse over an element.
  - CSS를 사용해서, element에 마우스를 올렸을 때 원하는 cursor style을 설정할 수 있다.
- For example, you can change your cursor into a hand icon, and much more, rather than using the default pointer.
  - 예를 들어 기본 포인터를 사용하는 대신, cursor를 손 모양 아이콘 등으로 변경할 수 있다.

<br>

- In the example below, the mouse pointer is set to a help icon when we mouse over the span element:
  - 아래 예제에서는, span element 위로 마우스를 가져가면 마우스 포인터가 도움말 아이콘으로 설정된다.

```html
<span style="cursor:help;">
   Do you need help?
</span>
```

<br>

- Result:

![img](/assets/img/css-sololearn-properties-12-01.png)

------

<br>

## The cursor Property Values

###### 마우스 cursor 속성 값

<br>

- There are numerous other possible values for the `cursor` property, such as:
  - 다음과 같이, `cursor` 속성에는 사용할 수 있는 다양한 값들이 있다.

<br>

- `default`: default cursor
  - cursor 기본값.
- `crosshair`: cursor displays as crosshair
  - cursor가 십자형으로 표시된다.
- `pointer`: cursor displays hand icon
  - cursor가 손 모양 아이콘으로 표시된다.

<br>

- The list of possible values is quite long.
  - 가능한 값의 list는 꽤 길다.
- The image below demonstrates the various available styles:
  - 아래 이미지는 사용 가능한 다양한 style을 보여준다.

![img](/assets/img/css-sololearn-properties-12-02.png)

<br>

> CSS allows you to set your desired cursor style when you mouse over an element.
>
> CSS를 사용해서, element에 마우스를 올렸을 때 원하는 cursor style을 설정할 수 있다.

------

<br>

## The default Value

###### 기본값

<br>

- Usually, the appearance of the mouse cursor is altered to provide a more interesting experience for website visitors.
  - 일반적으로 마우스 cursor의 모양이 변경되어, 웹사이트 방문자에게 보다 재미있는 경험을 제공한다.
- However, choosing the wrong cursor style can be misleading, as well.
  - 하지만 잘못된 cursor를 선택하면 오해의 소지가 있다.

<br>

- For example, if the cursor value is set to `default`, users may not "see" the links.
  - 예를 들어 cursor 값이 `default`로 설정된 경우, 사용자는 link를 볼 수 없다.

![img](/assets/img/css-sololearn-properties-12-03.png)

<br>

> Choose your mouse cursor styles carefully.
>
> 신중하게 마우스 cursor를 선택해라.

------

<br>

## QUIZ

- Which property allows to change the style of the mouse cursor?
  - 마우스 커서의 style을 변경할 수 있는 속성은 무엇인가?

> `cursor`

<br>

- What value of the cursor property displays a plus icon?
  - cursor 속성의 어떤 값에 plus 아이콘이 표시되는가?

> `crosshair`

<br>

- Drag and drop from the options below to make the cursor appear as a pointer on paragraphs:
  - cursor를 토막글에 포인터로 나타나게 만들어라.

```css
p {
   cursor: pointer;
}
```

<br>
