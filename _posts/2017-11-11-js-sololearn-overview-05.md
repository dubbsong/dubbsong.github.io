---
layout: post
title: "05. JavaScript 주석 (Overview)"
categories: javascript
tags: js
---

###### [SoloLearn](https://www.sololearn.com) JS 번역

<br>

# JavaScript Comments

###### JavaScript 주석

<br>

- Not all JavaScript statements are "executed".
  - 모든 JavaScript 문이 "실행되는" 것은 아니다.
- Code after a double slash //, or between /* and */, is treated as a `comment`.
  - 이중 슬래시 //, /*와 */ 사이의 코드는 `주석`으로 간주된다.
- Comments are ignored, and are not executed.
  - 주석은 무시되고, 실행되지 않는다.

<br>

- `Single line` comments use double slashes.
  - `한 줄` 주석은 이중 슬래시를 사용한다.

```html
<script>
	// This is a single line comment
   alert("This is an alert box!");
</script>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-js-overview-05-01.png)

------

<br>

## Multiple-Line Comments

###### 여러 줄 주석

<br>

- Everything you write between /* and */ will be considered as a multi-line comment.
  - /*와 */ 사이에 쓰는 모든 것은 여러 줄 주석으로 간주된다.

<br>

- Example:

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
  - 한 줄 주석은 어떻게 생겼나?

> `// this is a comment`

<br>

- Create a multi-line comment in JavaScript.
  - JavaScript에서 여러 줄 주석을 생성해라.

```js
/* this is a 
multiline
comment */
```

<br>