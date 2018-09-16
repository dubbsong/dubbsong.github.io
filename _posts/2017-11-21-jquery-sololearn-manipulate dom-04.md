---
layout: post
title: "(Manipulate DOM 04) Module 4 Quiz"
categories: jquery
---

###### [SoloLearn](https://www.sololearn.com/) jQuery 번역

<br>

## QUIZ

- How many siblings does the \<p> element with the id="txt" have in the following HTML?
  - 다음 HTML에서 id="txt" \<p> element에 얼마나 많은 siblings(형제)가 있는가?

```html
<div>
   <p></p>
   <p id="txt"></p>
   <p></p>
</div>
```

> `2`

<br>

- Fill in the blanks to select the first child of the div element.
  - div element의 첫 번째 child(자식)을 선택해라.

```js
$("div").children().eq(0);
```

<br>

- Drag and drop from the options below to remove all children of the paragraph tag.
  - 토막글 태그의 모든 children(자식)을 제거해라.

```js
$("p").children().remove();
```

<br>

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```html
<div><p>1</p></div>
<div>2</div>

<script>
   alert($("p").parent().siblings().eq(0).text());
</script>
```

> `2`

<br>