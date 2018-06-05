---
layout: post
title: "SoloLearn 번역 - 01. font-family (Working with Text)"
categories: dev
tags: css
---

## The font-family Property

- The font-family property specifies the font for an element.
  - font-family 속성은 element의 font를 지정한다.
- There are two types of font family names:
  - font family 이름에는 두 가지 타입이 있다.

<br>

1. **font family**: a specific font family (like Times New Roman or Arial)
   - 특정 font family (Times New Roman 또는 Arial)
2. **generic family**: a group of font families with a similar look (like Serif or Monospace)
   - 비슷한 모양을 가진 font family 그룹 (Serif 또는 Monospace)

<br>

- Here is an example of different font styles:
  - 다음은 다양한 font 스타일의 예이다.

![SoloLearn img](/assets/img/sololearn-css-working with text-01-01.png)

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

<br>

- Result:

![SoloLearn img](/assets/img/sololearn-css-working with text-01-02.png)

<br>

> Separate each value with a **comma** to indicate that they are alternatives.
>
> 각 값을 **콤마**로 구분해서 대체 값임을 나타낸다.

> If the name of a font family is more than one word, it must be in quotation marks: "Times New Roman".
>
> font family 이름이 두 단어 이상인 경우, 따옴표로 묶어야 한다.

------

<br>

## The font-family Property 02

- The font-family property should hold several font names as a "fallback" system.
  - font-family 속성은 "fallback" 시스템으로 여러 font 이름을 포함해야 한다.
- When specifying a web font in a CSS style, add more than one font name, in order to avoid unexpected behaviors.
  - CSS 스타일로 웹 font를 지정할 때, 예기치 않은 동작을 피하기 위해, 둘 이상의 font 이름을 추가해라.
- If the client computer for some reason doesn't have the one you choose, it will try the next one.
  - 어떤 이유로 클라이언트 컴퓨터에 선택한 font 없다면, 다음 font를 시도한다.

<br>

- It is a good practice to specify a generic font family, to let the browser pick a similar font in the generic family, if no other fonts are available.
  - 사용 가능한 다른 font들이 없다면, 브라우저가 일반 family에서 유사한 font를 선택하도록 일반 font family를 지정하는 것이 좋다.

```css
body {
   font-family: Arial, "Helvetica Neue", Helvetica, sans-serif;
}
```

<br>

- If the browser does not support the font **Arial**, it tries the next fonts (**Helvetica Neue**, then **Helvetica**).
  - 브라우저가 **Arial** font를 지원하지 않는다면, 다음 font들(**Helvetica Neue**, 그 다음에 **Helvetica**)을 시도한다.
- If the browser doesn't have any of them, it will try the generic **sans-serif**.
  - 브라우저에 포함되어 있지 않으면, 일반 **sans-serif**를 시도한다.

<br>

> Remember to use quotation marks if the font name consists of more than one word.
>
> font 이름이 둘 이상의 단어로 구성된 경우, 따옴표를 사용해라.

------

<br>

## QUIZ

- Drag and drop from the options below to make the font of the paragraph "Arial":

```css
p {
   font-family: Arial;
}
```

<br>

- Why is the name of one of the fonts put in quotes?
  - it shows a font family
  - **it consists of two or more words**
  - to support "fallback"
  - it is a rarely used font

<br>