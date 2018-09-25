---
layout: post
title: "(Text 12) text-transform 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS text-transform Property

###### text-transform 속성

<br>

- The text-transform CSS property specifies how to capitalize an element's text.
  - text-transform CSS 속성은 element의 텍스트를 대문자로 사용하는 방법을 지정한다.
- For example, it can be used to make text appear with each word capitalized.
  - 예를 들어, 각 단어를 대문자로 텍스트를 나타내는 데 사용할 수 있다.

<br>

- HTML:

```html
<p class="capitalize">
   The value capitalize transforms the first
   character in each word to uppercase;
   all other characters remain unaffected.
</p>
```

<br>

- CSS:

```css
p.capitalize {
   text-transform: capitalize;
}
```

[코드 실행 확인](https://code.sololearn.com/529/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-12-01.png)

------

<br>

## text-transform Values

###### text-transform 값

<br>

- Using text-transform property you can make text appear in all-uppercase or all-lowercase.
  - text-transform 속성을 사용해서 텍스트를 모두 대문자 또는 모두 소눔자로 나타낼 수 있다.

<br>

- HTML:

```html
<p class="uppercase">This value transforms all characters to uppercase. </p>
<p class="lowercase">This value transforms all characters to lowercase. </p>
```

<br>

- CSS:

```css
p.uppercase {
   text-transform: uppercase;
}

p.lowercase {
   text-transform: lowercase;
}
```

[코드 실행 확인](https://code.sololearn.com/530/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-12-02.png)

<br>

> The value `none` will produce no capitalization effect at all.
>
> `none` 값은 대문자 효과를 전혀 발생시키지 않는다.

------

<br>

## QUIZ

- Drag and drop from the options below to make each word capitalized in the paragraph:
  - 토막글의 각 단어를 대문자로 만들어라.

```css
p.capfirst {
   text-transform: capitalize;
}
```

<br>

- Which option is NOT supported by the text-transform property?
  - text-transform 속성에서 지원되지 않는 옵션은 무엇인가?

> [ ] none
>
> [ ] uppercase
>
> [ ] capitalize
>
> [ ] `small-caps`

<br>
