---
layout: post
title: "(Text 03) font-style 속성"
caategories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS font-style Property

###### font-style 속성

<br>

- The font-style property is typically used to specify italic text.
  - font-style 속성은 일반적으로 italic(기울임 글꼴) 텍스트를 지정하는 데 사용된다.

<br>

- The HTML:

```html
<p class="italic">This is a paragraph in italic style. </p>
```

<br>

- The CSS:

```css
p.italic {
   font-style: italic;
}
```

[코드 실행 확인](https://code.sololearn.com/514/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-03-01.png)

<br>

<br>

- The font-style property has three values: `normal`, `italic`, and `oblique`.
  - font-style 속성은 `normal`, `italic`, `oblique`의 세 가지 값을 가진다.
- Oblique is very similar to italic, but less supported.
  - Oblique는 italic과 매우 비슷하지만, 덜 지원한다.

<br>

- The HTML:

```html
<p class="normal">This paragraph is normal. </p>
<p class="italic">This paragraph is italic. </p>
<p class="oblique">This paragraph is oblique. </p>
```

<br>

- The CSS:

```css
p.normal {
   font-style: normal;
}

p.italic {
   font-style: italic;
}

p.oblique {
   font-style: oblique;
}
```

[코드 실행 확인](https://code.sololearn.com/515/#css)

<br>

> The HTML `<i>` tag will produce exactly the same result as the `italic font style`.
>
> HTML `<i>` 태그는 `italic font style`과 동일한 결과를 생성한다.

------

<br>

## QUIZ

- Make the text italic:
  - 텍스트를 italic으로 만들어라.

```css
#styled {
   font-style: italic;
}
```

<br>

- What value is NOT used with the font-style property?
  - font-style 속성에는 어떤 값을 사용하지 않는가?

> [ ] italic
>
> [ ] `slant`
>
> [ ] oblique
>
> [ ] normal

<br>
