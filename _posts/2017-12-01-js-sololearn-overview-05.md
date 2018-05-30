---
layout: post
title: "SoloLearn 번역 - 05. Comments in JavaScript (Overview)"
categories: javascript
tags: JS
---

## JavaScript Comments (JS 주석)

- Not all JavaScript statements are "executed".
  - 모든 JavaScript 문이 "실행"되는 것은 아니다.
- Code after a double slash //, or between /* and */, is treated as a **comment**.
  - 더블 슬래시 // 또는 /*와 */ 사이의 코드는 **주석**으로 처리된다.
- Comments are ignored, and are not executed.
  - 주석은 무시되고, 실행되지 않는다.

<br>

- **Single line** comments use double slashes.
  - **한 줄** 주석은 더블 슬래시를 사용한다.

```html
<script>
	// This is a single line comment
   alert("This is an alert box!");
</script>
```

<br>

- Result:

![SoloLearn img](/assets/img/sololearn05-1.png)

------

<br>

## Multiple-Line Comments (다행 주석)

- Everything you write between /* and */ will be considered as a multi-line comment.
  - /*와 */ 사이에 작성하는 모든 것은 다행 주석으로 간주된다.

<br>

- Here is an example.

```html
<script>
	/* This code
	creates an
	alert box */
   alert("This is an alert box!");
</script>
```

<br>

> Comments are used to describe and explain what the code is doing.
>
> 주석은 코드가 하는 일을 기술하고 설명하는 데 사용된다.

------

<br>

## QUIZ

- How does the single line comment look like?
  - \<!-- this is a comment-->
  - %%this is a commnet
  - **// this is a commnet**
  - **this is a comment

<br>

- Create a multi-line comment in JavaScript.

```javascript
/* this is a
multiline
comment */
```

<br>