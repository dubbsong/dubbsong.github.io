---
layout: post
title: "(Overview 05) 주석"
categories: js
---

###### [SoloLearn](https://www.sololearn.com/) JS 번역

<br>

### JavaScript Comments

###### JS 주석

<br>

- Not all JavaScript statements are "executed".
  - 모든 JS 문이 "실행"되는 것은 아니다.
- Code after a double slash //, or between /* and */, is treated as a `comment`.
  - 이중 슬래시 // 또는 /*와 */ 사이의 코드는, `주석`으로 처리된다.
- Comments are ignored, and are not executed.
  - 주석은 무시되고, 실행되지 않는다.

<br>

- `Single line comments` use double slashes.
  - `한 줄 주석`은 이중 슬래시를 사용한다.

```html
<script>
  // This is a single line comment
  alert("What's up?");
</script>
```

[코드 실행 확인](https://code.sololearn.com/645/#js)

------

<br>

## Multiple-Line Comments

###### 여러 줄 주석

<br>

- Everything you write between /* and */ will be considered as a multi-line comment.
  - /* 와 */ 사이에 작성하는 모든 것은, 여러 줄 주석으로 간주된다.

```html
<script>
  /* This code
  creates an
  alert box */
  alert("What's up?");
</script>
```

[코드 실행 확인](https://code.sololearn.com/646/#js)

<br>

> Comments are used to describe and explain what the code is doing.
>
> 주석은 코드가 수행하는 것을 설명하는 데 사용된다.

------

<br>

## QUIZ

- How does the single line comment look like?
  - 한 줄 주석은 어떻게 생겼는가?

> `// this is a comment`

<br>

- Create a multi-line comment in JavaScript.
  - JS의 여러 줄 주석을 생성해라.

```js
/* this is a 
multi-line
comment */
```

<br>