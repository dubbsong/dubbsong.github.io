---
layout: post
title: "(Text 02) font-size 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS font-size Property

###### font-size 속성

<br>

- The font-size property sets the size of a font.
  - font-size 속성은 글꼴의 사이즈를 설정한다.
- One way to set the size of fonts on the web is to use `keywords`.
  - 웹에서 글꼴 사이즈를 설정하는 한 가지 방법은 `keyword`를 사용하는 것이다.
  - `xx-small`, `small`, `medium`, `large`, `larger`, etc

<br>

- The HTML:

```html
<p class="small">
   토막글 텍스트를 작게 설정한다
</p>
<p class="medium">
   토막글 텍스트를 중간으로 설정한다
</p>
<p class="large">
   토막글 텍스트를 크게 설정한다
</p>
<p class="xlarge">
   토막글 텍스트를 아주 크게 설정한다
</p>
```

<br>

- The CSS:

```css
p.small {
   font-size: small;
}

p.medium {
   font-size: medium;
}

p.large {
   font-size: large;
}

p.xlarge {
   font-size: x-large;
}
```

[코드 실행 확인](https://code.sololearn.com/511/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-02-01.png)

<br>

> Keywords are useful if you do not want the user to be able to increase the size of the font because it will adversely affect your site's appearance.
>
> keyword는 사용자가 글꼴의 사이즈를 늘릴 수 없도록 하려는 경우에 유용하다.
>
> 사이트의 모양에 부정적인 영향을 미치기 때문이다.

<br>

<br>

- You can also use numerical values in `pixels` or `ems` to manipulate font size.
  - `픽셀` 또는 `em`의 숫자 값을 사용해서, 글꼴 사이즈를 조작할 수도 있다.
- Setting the font size in pixel values (`px`) is a good choice when you need pixel accuracy, and it gives you full control over the text size.
  - 정확한 픽셀이 필요할 때 글꼴 사이즈를 픽셀 값(`px`)으로 설정하면, 텍스트 사이즈를 완벽하게 제어할 수 있다.
- The `em` size unit is another way to set the font size (`em` is a relative size unit).
  - `em` 사이즈 단위는 글꼴 사이즈를 설정하는 또 다른 방법이다.
  - (`em`은 상대적 사이즈 단위이다)
- It allows all major browsers to resize the text.
  - 모든 주요 브라우저가 텍스트의 사이즈를 조정할 수 있다.
- If you haven't set the font size anywhere on the page, then it is the browser default size, which is `16px`.
  - 페이지의 어느 곳에서나 글꼴 사이즈를 설정하지 않는 경우, 브라우저 기본 사이즈는 `16px`이다.

<br>

- To calculate the em size, just use the following formula: `em = pixels / 16`
  - em 사이즈를 계산하려면, 다음 공식을 사용해라: `em = pixels / 16`

<br>

- For example:

```css
h1 {
   font-size: 20px;
}
```

[코드 실행 확인](https://code.sololearn.com/512/#css)

<br>

```css
h1 {
   font-size: 1.25em;
}
```

[코드 실행 확인](https://code.sololearn.com/513/#css)

<br>

- Both of the examples will produce the same result in the browser, because `20/16 = 1.25em`.
  - `20/16 = 1.25em`이므로, 두 예제 모두 브라우저에서 동일한 결과를 보여준다.

------

<br>

## QUIZ

- Set the font-size of the paragraph to 15px;
  - 토막글의 font-size를 15px로 설정해라.

```css
p { font-size: 15px; }
```

<br>