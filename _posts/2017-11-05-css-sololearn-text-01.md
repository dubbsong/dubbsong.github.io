---
layout: post
title: "(Text 01) font-family 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS font-family Property

###### font-family 속성

<br>

- The font-family property specifies the font for an element.
  - font-family 속성은 element의 글꼴을 지정한다.
- There are two types of font family names:
  - font family 이름에는 두 가지 type이 있다.

> `font family`: a specific font family (특정 글꼴 집합)
>
> `generic family`: a group of font families with a similar look (비슷한 모양을 가진 글꼴 집합 그룹)

<br>

- Here is an example of different font styles:
  - 다음은 다양한 글꼴 style의 예제이다.

![img](/assets/img/css-sololearn-text-01-01.png)

<br>

- The HTML:

```html
<p class="serif">
   This is a paragraph shown in serif font.
</p>
<p class="sansserif">
   This is a paragraph shown in sans-serif font.
</p>
<p class="monospace">
   This is a paragraph shown in monospace font.
</p>
<p class="cursive">
   This is a paragraph shown in cursive font.
</p>
<p class="fantasy">
   This is a paragraph shown in fantasy font.
</p>
```

<br>

- The CSS:

```css
p.serif {
   font-family: "Times New Roman", Times, serif;
}

p.sansserif {
   font-family: Helvetica, Arial, sans-serif;
}

p.monospace {
   font-family: "Courier New", Courier, monospace;
}

p.cursive {
   font-family: Florence, cursive;
}

p.fantasy {
   font-family: Blippo, fantasy;
}
```

[코드 실행 확인](https://code.sololearn.com/510/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-01-02.png)

<br>

> Separate each value with a `comma` to indicate that they are alternatives.
>
> 각 값을 `쉼표`로 구분해서, 대체 값임을 나타낸다.

> If the name of a font family is more than one word, it must be in quotation marks: `"Times New Roman"`
>
> font family의 이름이 둘 이상의 단어인 경우, 따옴표로 묶어야 한다: `"Times New Roman"`

<br>

<br>

- The font-family property should hold several font names as a "fallback" system.
  - font-family 속성은 "fallback" 시스템으로 여러 글꼴 이름을 포함해야 한다.
- When specifying a web font in a CSS style, add more than one font name, in order to avoid unexpected behaviors.
  - CSS style로 웹 글꼴을 지정할 때, 예기치 않은 동작을 피하기 위해, 둘 이상의 글꼴 이름을 추가해라.
- If the client computer for some reason doesn't have the one you choose, it will try the next one.
  - 클라이언트 컴퓨터에 선택한 글꼴이 없는 경우, 다음 글꼴을 시도한다.

<br>

- It is a good practice to specify a generic font family, to let the browser pick a similar font in the generic family, if no other fonts are available.
  - 사용 가능한 글꼴이 없으면, 브라우저가 generic family에서 유사한 글꼴을 선택하도록 font family를 지정하는 것이 좋다.

```css
body {
   font-family: Arial, "Helvetica Neue", Helvetica, sans-serif;
}
```

<br>

- If the browser does not support the font `Arial`, it tries the next fonts (`Helvetica Neue`, then `Helvetica`).
  - 브라우저가 `Arial` 글꼴을 지원하지 않는다면, 다음 글꼴(`Helvetica Neue`, 그다음 `Helvetica`)을 시도한다.
- If the browser doesn't have any of them, it will try the generic `sans-serif`.
  - 브라우저에 포함되어 있지 않다면, 일반 `sans-serif`를 시도한다.

<br>

> Remember to use quotation marks if the font name consists of more than one word.
>
> 글꼴 이름이 둘 이상의 단어로 구성된 경우, 따옴표를 사용해라.

------

<br>

## QUIZ

- Drag and drop from the options below to make the font of the paragraph "Arial":
  - 토막글 "Arial"의 글꼴을 만들어라.

```css
p {
   font-family: Arial;
}
```

<br>

- Why is the name of one of the fonts put in quotes?
  - 글꼴 중 하나의 이름이 따옴표로 묶여 있는 이유는 무엇인가?

> `it consists of two or more words`
>
> 둘 이상의 단어로 구성되었기 때문

<br>