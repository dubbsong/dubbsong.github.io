---
layout: post
title: "(Text 15) white-space 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS white-space Property

###### white-space 속성

<br>

- The white-space property specifies how white-space inside an element is handled.
  - white-space 속성은 element 내의 여백을 처리하는 방법을 지정한다.
- The values can be set as `normal`, `inherit`, `nowrap`, etc.
  - 값은 `normal`, `inherit`, `nowrap` 등으로 설정할 수 있다.

<br>

- The `nowrap` value makes the text continue on the same line until a \<br> tag is encountered, and also collapses all sequences of whitespace into a single whitespace.
  - `nowrap` 값은 \<br> 태그를 마주칠 때가지 텍스트를 같은 줄에서 계속 만들고, 여백의 모든 sequence를 하나의 여백으로 축소한다.

<br>

- HTML:

```html
<p>
   This paragraph has	multiple spaces	and
   a line break, but it will be ignored, as we used the nowrap value.
</p>
```

<br>

- CSS:

```css
p {
   white-space: nowrap;
}
```

[코드 실행 확인](https://code.sololearn.com/535/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-15-01.png)

<br>

> The text will continue on the same line until a `<br />` tag is encountered.
>
> `<br />` 태그를 마주칠 때까지 텍스트는 같은 줄에서 계속된다.

------

<br>

## The white-space Values

###### white-space 값

<br>

- The white-space property also supports other values:
  - white-space 속성은 다른 값도 지원한다.

<br>

- `pre`: text will only wrap on line breaks and white space
- `pre-line`: text will wrap where there is a break in code, but extra white space is still ignored
- `pre-wrap`: text will wrap when necessary, and on line breaks

<br>

- HTML:

```html
<p class="pre">
   In the markup we have multiple	spaces
   and a line break.
</p>

<p class="preline">
   In the markup we have multiple	spaces
   and a line break, but in the result multiple spaces are ignored.
</p>

<p class="prewrap">
   In the markup we have	multiple
   spaces and a line break.
</p>
```

<br>

- CSS:

```css
p.pre {
   white-space: pre;
}

p.preline {
   white-space: pre-line;
}

p.prewrap {
   white-space: pre-wrap;
}
```

[코드 실행 확인](https://code.sololearn.com/536/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-text-15-02.png)

<br>

> `pre-wrap` value behaves as the `pre` value, except that it adds extra line breaks to prevent the text breaking out of the element's box.
>
> `pre-wrap` 값은 `pre` 값으로 작동한다.
>
> element의 상자 밖으로 텍스트가 튀는 것을 방지하기 위해 줄 바꿈을 추가한다는 점만 다르다.

------

<br>

## QUIZ

- Which of the following indicate the purpose of the "nowrap" option?
  - 다음 중 "nowrap" 옵션의 목적을 나타내는 것은 어떤 것인가?

> [ ] It separates paragraphs (토막글을 구분한다)
>
> [ ] `It puts the whole text in one line` (전체 텍스트를 한 줄에 놓는다)
>
> [ ] `It collapses all sequences of whitespace into a single whitespace` (여백의 모든 sequence를 하나의 여백으로 축소한다)

<br>

- What is the difference between the "pre" and "pre-line" options?
  - "pre"와 "pre-line" 옵션의 차이점은 무엇인가?

> `"pre" accepts all line-breaks and whitespace, while "pre-line" ignores the whitespace`
>
> "pre"는 모든 줄 바꿈과 여백을 허용하고, "pre-line"은 여백을 무시한다.

<br>