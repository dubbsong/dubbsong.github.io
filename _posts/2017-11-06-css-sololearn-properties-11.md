---
layout: post
title: "(Properties 11) Styling the Links"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS Styling the Links

------

<br>

<br>

## Setting Styles to Links

###### link style 설정

<br>

- Links can be styled with any CSS property (e.g., color, font-family, background, etc.).
  - link는 CSS 속성(예: color, font-family, background 등)으로 style을 지정할 수 있다.
- In addition, links can be styled differently, depending on what state they are in.
  - 게다가, link의 상태에 따라 다르게 스타일을 지정할 수 있다.
- The following pseudo selectors are available:
  - 다음 의사(pseudo) selector를 사용할 수 있다.

<br>

- `a:link` - defines the style for normal unvisited links
  - 방문하지 않은 link의 style을 정의한다.
- `a:visited` - defines the style for visited links
  - 방문한 link의 style을 정의한다.
- `a:active` - a link becomes active once you click on it
  - 클릭하면 link가 활성화된다.
- `a:hover` - a link is hovered when the mouse is over it
  - 마우스가 위에 있을 때 link가 hover 된다.

<br>

- The example below creates a link that will change the style when the mouse is moved over it.
  - 아래 예제는 마우스를 위로 움직일 때 style을 변경할 link를 생성한다.

<br>

- HTML:

```html
<p>
   <a href="https://www.sololearn.com" target="_blank">
      This link is hovered when we mouse over it
   </a>
</p>
```

<br>

- CSS:

```css
a:hover {
   color: red;
}
```

[코드 실행 확인](https://code.sololearn.com/560/#css)

<br>

- The link from the above example would look like this:
  - 위 예제의 link는 다음과 같다.

![img](/assets/img/css-sololearn-properties-11-01.png)

<br>

- But when we mouse over it, it becomes red, as we defined in our stylesheet.
  - 하지만 그 위에 마우스를 올리면, stylesheet에서 정의한 것처럼 빨갛게 된다.

![img](/assets/img/css-sololearn-properties-11-02.png)

<br>

> When setting the style for several link states, there are some order rules:
>
> 여러 link 상태에 대한 style을 설정할 때, 몇 가지 순서 규칙이 있다.

> `a:hover` MUST come after `a:link` and `a:visited`
>
> `a:hover`는 `a:link`와 `a:visited` 뒤에 와야 한다.

> `a:active` MUST come after `a:hover`
>
> `a:active`는 `a:hover` 뒤에 와야 한다.

------

<br>

## Link's Text Decoration

###### text-decoration 속성

<br>

- By default, text links are underlined by the browser.
  - 기본적으로 브라우저에서 텍스트 link에는 밑줄이 있다.
- One of the most common uses of CSS with links is to `remove the underline`.
  - link가 있는 CSS의 가장 일반적인 용도 중 하나는 `밑줄을 제거하는 것`이다.
- In the example below, the `text-decoration` property is used to remove the underline.
  - 아래 예제에서는 `text-decoration` 속성을 사용해서 밑줄을 제거한다.

<br>

- HTML:

```html
<p>
   <a href="https://www.sololearn.com" target="_blank">
      This link has no underline.
   </a>
</p>
```

<br>

- CSS:

```css
a:link {
   text-decoration: none;
}
```

[코드 실행 확인](https://code.sololearn.com/561/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-11-03.png)

<br>

> The following properties are used to control the look and feel of links:
>
> 다음과 같은 속성을 사용해서 link의 모양과 느낌을 제어한다.

> `border:none` - removes border from images with links
>
> link가 있는 이미지에서 border를 제거한다.

> `outline:none` - removes the dotted border on clicked lines in IE
>
> IE에서 클릭된 줄의 dotted border를 제거한다.

------

<br>

## QUIZ

- Of what type are the :link, :visited, :active and :hover selectors?
  - :link, :visited, :active, :hover selector는 어떤 type인가?

> `pseudo`

<br>

- What value is used to remove borders of images with links?
  - link를 사용해서 이미지의 border를 제거하는 데 사용되는 값은 무엇인가?

> `border: none;`

<br>