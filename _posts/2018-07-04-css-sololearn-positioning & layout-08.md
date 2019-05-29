---
layout: post
title: "(Positioning & Layout 08) Module 4 Quiz"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

## QUIZ

- If you give a negative value to the "top" property, in which direction will the box be moved?
  - "top" 속성에 음수 값을 지정하면, box가 어느 방향으로 이동하는가?

> `up`

<br>

- When the "float" property is used with the values of "left" or "right", anything else that lives in the containing element will:
  - "float" 속성이 "left" 또는 "right" 값과 함께 사용되면, 포함 element에 있는 다른 모든 element는 다음과 같다.

> `flow around the element associated with the "float" property`
>
> "float" 속성과 관련된 element 주위를 흐른다

<br>

- When the text needs more space than the dimensions of the box, the browser shows scrolls for the overflow property with the values of "scroll" and:
  - 텍스트가 box의 크기보다 더 많은 공간을 필요로 할 때, 브라우저는 "scroll" 값과 ... 값을 함께 overflow 속성에 대한 scroll을 보여준다.

> `auto`

<br>

- Assign width of 500px to the "text" element and enable fixed scrollbars:
  - "text" element에 width 500px을 할당하고, fixed scrollbar를 사용할 수 있게 만들어라.

```css
#text {
   overflow: scroll;
   height: 200px;
   width: 500px;
}
```

<br>

- Fill in the blanks and make the blue box disappear from the webpage:
  - 웹페이지에서 파란색 box를 사라지게 만들어라.

```css
#red {
   position: absolute;
   top: 100px;
   left: 100px;
   z-index: 20;
}

#blue {
   position: relative;
   z-index: 50;
   display: none;
}
```

<br>