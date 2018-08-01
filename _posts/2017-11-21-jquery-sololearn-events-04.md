---
layout: post
title: "SoloLearn jQuery 번역 - 04. Module 5 Quiz (Events)"
categories: dev
tags: jquery
---

## QUIZ

- Fill in the blanks to add an event handler to the paragraph.
  - p에 이벤트 핸들러를 추가해라.

```js
$("p").on("click", function() {
   // some code
});
```

<br>

- What will be the output after the div is clicked two times?
  - div가 두 번 클릭된 후 출력은 무엇이 되는가?

```html
<div>1</div>

<script>
   $("div").click(function() {
      $("div").text($("div").text()+1);
   });
</script>
```

> [ ] 3
>
> [ ] 1
>
> [ ] 11
>
> [ ] `111`

<br>

- Fill in the blanks to remove the "click" event handler from all \<a> elements.
  - 모든 \<a> element에서 "click" 이벤트 핸들러를 제거해라.

```js
$("a").off("click");
```

<br>

- How many "a" characters will be output after the div is clicked three times?
  - div가 세 번 클릭된 후 "a" 문자가 몇 번 출력되는가?

```html
<div>a</div>

<script>
   $("div").click(function() {
      $("div").append("a");
      $("div").off("click");
   });
</script>
```

> `2`

<br>