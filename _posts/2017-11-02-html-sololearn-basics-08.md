---
layout: post
title: "SoloLearn HTML 번역 - 08. Links (Basics)"
categories: dev
tags: html
---

## The \<a> Tag

###### \<a> 태그

<br>

- Links are also an integral part of every web page.
  - 링크는 모든 웹 페이지에서 없어서는 안 될 부분이다.
- You can add links to text or images that will enable the user to click on them in order to be directed to another file or web page.
  - 사용자가 다른 파일이나 웹 페이지로 이동하기 위해 클릭할 수 있는 텍스트나 이미지에 링크를 추가할 수 있다.
- In HTML, links are defined using the `<a>` tag.
  - HTML에서 링크는 `<a>` 태그를 사용해서 정의된다.

<br>

- Use the `href` attribute to define the link's destination address:
  - `href` 속성을 사용해서 링크의 수신지 주소를 정의해라.

```html
<a href=""></a>
```

------

<br>

## Creating Your First Link

###### 첫 번째 링크 만들기

<br>

- In the example below, a link to SoloLearn's website is defined:
  - 아래 예제에서, SoloLearn의 웹사이트에 대한 링크가 정의된다.

```html
<a href="http://www.sololearn.com"> Learn Playing </a>
```

<br>

- Once the code has been saved, "Learn Playing" will display as a link: [Learn Playing](www.sololearn.com)
  - 코드가 저장되면, "Learn Playing"이 링크로 표시된다.
- Clicking on `"Learn Playing"` redirects you to www.sololearn.com
  - `"Learn Playing"`을 클릭하면 www.sololearn.com으로 리다이렉트된다.

<br>

> Links can be either absolute or relative.
>
> 링크는 절대적이거나 상대적일 수 있다.

------

<br>

## The target Attribute

###### target 속성

<br>

- The `target` attribute specifies where to open the linked document.
  - `target` 속성은 링크된 문서를 여는 위치를 지정한다.
- Giving a `_blank` value to your attribute will have the link open in a new window or new tab.
  - 속성에 `_blank` 값을 지정하면 링크가 새 창이나 새 탭에 열린다.

```html
<a href="http://www.sololearn.com" target="_blank">
	Learn Playing
</a>
```

------

<br>

## QUIZ

- What tag is used to create a link to a web page?
  - 어떤 태그가 웹 페이지에 대한 링크를 만드는 데 사용되는가?

> \<a href="">

<br>

- Which attribute of the link tag contains the URL location that you are trying to link to?
  - 링크하려는 URL 위치는 링크 태그의 어떤 속성이 포함하는가?

> [x] `href`
>
> [ ] location
>
> [ ] target
>
> [ ] address

<br>

- Which value of the target attribute makes the link open in a new tab or a new window?
  - target 속성의 어떤 값으로 새 탭이나 새 창을 열 수 있는가?

```html
<a href="2.html" target="_blank">
```

<br>