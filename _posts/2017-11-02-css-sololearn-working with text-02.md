---
layout: post
title: "SoloLearn 번역 - 02. font-size (Working with Text)"
categories: dev
tags: css
---

## The font-size Property

- The font-size property sets the size of a font.
  - font-size 속성은 font의 크기를 설정한다.
- One way to set the size of fonts on the web is to use **keywords**.
  - 웹에서 font 크기를 설정하는 한 가지 방법은 **keyword**를 사용하는 것이다.
- For example **xx-small, medium, large, larger**, etc.
  - 예를 들어 **xx-small, medium, large, larger** 등이 있다.

<br>

- The HTML:

```html
<p class="small">
   Paragraph text set to be small
</p>
<p class="medium">
   Paragraph text set to be medium
</p>
<p class="large">
   Paragraph text set to be large
</p>
<p class="xlarge">
   Paragraph text set to be very large
</p>
```

<br>

- The CSS:

```css
p.small {
   font-size: small;
}
p.mediup {
   font-size: medium;
}
p.large {
   font-size: large;
}
p.xlarge {
   font-size: x-large;
}
```

<br>

- Result:

![SoloLearn img](/assets/img/sololearn-css-working with text-02-01.png)

<br>

> Keywords are useful if you do not want the user to be able to increase the size of the font because it will adversely affect your site's appearnce.
>
> 유저가 font 크기를 늘릴 수 없도록 하려는 경우, keword가 유용하다.
>
> 이는 사이트의 모양에 좋지 않은 영향을 미치기 때문이다.

------

<br>

## The font-size Property 02

- You can also use numerical values in **pixels** or **ems** to manipulate font size.
  - font 크기를 조작하기 위해 **pixel** 또는 **em**의 숫자 값을 사용할 수도 있다.
- Setting the font size in pixel values (**px**) is a good choice when you need pixel accuracy, and it gives you full control over the text size.
  - 픽셀 정확도가 필요할 때, font 크기를 픽셀 값(**px**)으로 설정하면 텍스트 크기를 완벽하게 제어할 수 있다.\
- The **em** size unit is another way to set the font size (**em** is a relative size unit).
  - **em** 크기 단위는 font 크기(**em**은 상대 크기 단위)를 설정하는 또 다른 방법이다.
- It allows all major browsers to resize the text.
  - 모든 주요 브라우저가 텍스트의 크기를 조정할 수 있다.
- If you haven't set the font size anywhere on the page, then it is the browser default size, which is **16px**.
  - 페이지의 어느 곳에서나 font 크기를 설정하지 않은 경우, 브라우저 기본 크기는 **16px**이다.

<br>

- To calculate the em size, just use the following formula: **em = pixels / 16**
  - em 크기를 계산하려면, 다음 공식을 사용해라: **em = pixels / 16**

<br>

- For example:

```css
h1 {
   font-size: 20px;
}
```

<br>

```css
h1 {
   font-size: 1.25em;
}
```

<br>

- Both of the examples will produce the same result in the browser, because **20/16 = 1.25em**.
  - **20/16 = 1.25em**이기 때문에 두 예제 모두 브라우저에서 동일한 결과를 생성한다.

<br>

> Try different combinations of text size and page zooming in a variety of browsers to ensure that the text remains readable.
>
> 다양한 브라우저에서 텍스트 크기와 페이지 확대/축소의 다른 조합을 시도해서 텍스트를 읽을 수 있도록 해라.

------

<br>

## QUIZ

- Rearrange the code to create a style rule:

```css
p {
   font-size: large;
}
```

<br>

- Set the font-size of the paragraph to 15px:

```css
p {
   font-size: 15px;
}
```

<br>