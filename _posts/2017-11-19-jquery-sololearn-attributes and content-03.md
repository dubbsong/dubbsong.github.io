---
layout: post
title: "03. 내용(content) 가져오기 & 설정하기 (Attributes and Content)"
categories: dev
tags: jquery
---

###### [SoloLearn](https://www.sololearn.com) jQuery 번역

<br>

# Get & Set Content

###### 내용(content) 가져오기 & 설정하기

<br>

## Get Content

###### 내용(content) 가져오기

<br>

- There are several methods for manipulating the content of HTML elements via jQuery.
  - jQuery를 통해 HTML element의 내용을 조작하는 몇 가지 방법이 있다.
- The `html()` method is used to get the content of the selected element, including the HTML markup.
  - `html()` 메소드는 HTML 마크업을 포함한 선택된 element의 내용을 가져오는 데 사용된다.

<br>

- HTML:

```html
<p>
   jQuery is <b>fun</b>
</p>
```

<br>

- JS:

```js
$(function() {
   var val = $("p").html();
   alert(val);
});

// alerts "jQuery is <b>fun</b>"
```

[코드 실행 확인 링크](https://code.sololearn.com/1106/#js)

<br>

- Notice, that the HTML markup (the \<b> tags) is also returned.
  - HTML 마크업(\<b> 태그)도 반환된다는 것을 주의해라.
- If you need only the text content, without the HTML markup, you can use the `text()` method:
  - HTML 마크업 없이 텍스트 내용만 필요하다면, `text()` 메소드를 사용할 수 있다.

```js
$(function() {
   var val = $("p").text();
   alert(val);
});

// alerts "jQuery is fun"
```

[코드 실행 확인 링크](https://code.sololearn.com/1107/#js)

<br>

> The `html()` and `text()` methods can be used for all HTML elements that can contain content.
>
> `html()`과 `text()` 메소드는 내용을 포함할 수 있는 HTML element에 사용할 수 있다.

------

<br>

## Set Content

###### 내용(content) 설정하기

<br>

- The same `html()` and `text()` methods can be used to change the content of HTML elements.
  - 동일한 `html()`과 `text()` 메소드를 사용해서 HTML element의 내용을 변경할 수 있다.
- The content to be set is provided as a parameter to the method.
  - 설정할 내용은 메소드에 대한 매개변수로 제공된다.

<br>

- HTML:

```html
<div id="test">
   <p>some text</p>
</div>
```

<br>

- JS:

```js
$(function() {
   $("#test").text("hello!");
});
```

[코드 실행 확인 링크](https://code.sololearn.com/1109/#html)

<br>

- The code above changes the content of the element with id="test" to "hello!".
  - 위의 코드는 id="test" element의 내용을 "hello!"로 변경한다.

<br>

> If the content you are setting contains HTML markup, you should use the `html()` method instead of `text()`.
>
> 설정한 내용에 HTML 마크업이 포함되어 있으면, `text()` 대신 `html()` 메소드를 사용해야 한다.

------

<br>

## QUIZ

- What is the output of this code?
  - 이 코드의 출력은 무엇인가?

```html
<div id="test">
   <p>p</p>
</div>
<script>
	alert($("test").text())
</script>
```

> `p`

<br>

- Fill in the blanks to change the content of the paragraphs with id="demo" to "\<b>Hi\</b>" maintaining the HTML markup.
  - id="demo"로 된 p의 내용을 "\<b>Hi\<b>"로 변경해라.
  - HTML 마크업을 유지하도록.

```js
$(function() {
   $("#demo").html("<b>Hi</b>");
});
```

<br>
