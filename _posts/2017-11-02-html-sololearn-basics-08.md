---
layout: post
title: "08. HTML 링크 (Basics)"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML Link

###### HTML 링크

------

<br>

<br>

## The \<a> Tag

###### \<a> 태그

<br>

- Links are also an integral part of every webpage.
  - 링크는 모든 웹페이지에서 없어서는 안 될 부분이다.
- You can add links to text or images that will enable the user to click on them in order to be directed to another file or webpage.
  - 사용자가 다른 파일이나 웹페이지로 이동하기 위해 클릭할 수 있는 텍스트나 이미지에 대한 링크를 추가할 수 있다.
- In HTML, links are defined using the \<a> tag.
  - HTML에서 링크는 \<a> 태그를 사용해서 정의된다.

<br>

- Use the `href` attribute to define the link's destination address:
  - `href` 속성을 사용해서 링크의 주소를 정의해라.

```html
<a href=""></a>
```

<br>

> To link an image to another document, simply nest the \<img> tag inside \<a> tags.
>
> 이미지를 다른 문서에 연결하려면, \<a> 태그 내에 \<img> 태그를 중첩하면 된다.

------

<br>

## Creating First Link

###### 링크 생성하기

<br>

- In the example below, a link to SoloLearn's website is defined:
  - 아래 예제에서 SoloLearn의 웹사이트에 대한 링크가 정의된다.

```html
<a href="http://www.sololearn.com">Learn Playing</a>
```

[코드 실행 확인](https://code.sololearn.com/23/#html)

<br>

- Once the code has been saved, "Learn Playing" will display as a link:
  - 코드가 저장되면, "Learn Playing"이 링크로 표시된다.

<br>

- Clicking on `"Learn Playing"` redirects you to www.sololearn.com
  - `"Learn Playing"`을 클릭하면 www.sololearn.com으로 리다이렉트 된다.

<br>

> Links can be either absolute or relative.
>
> 링크는 절대 경로 또는 상대 경로일 수 있다.

------

<br>

## The target Attribute

###### target 속성

<br>

- The `target` attribute specifies where to open the linked document.
  - `target` 속성은 링크된 문서를 여는 위치를 지정한다.
- Giving a `_blank` value to your attribute will have the link open in a new window or new tab:
  - 속성에 `_blank` 값을 지정하면, 링크가 새 창이나 새 탭에서 열린다.

```html
<a href="http://www.sololearn.com" target="_blank">
   Learn Playing
</a>
```

[코드 실행 확인](https://code.sololearn.com/24/#html)

<br>

> A visited link is underlined and purple.
>
> 방문한 링크에는 밑줄이 생기고, 보라색이 된다.

------

<br>

## QUIZ

- What tag is used to create a link to a webpage?
  - 어떤 태그가 웹페이지에 대한 링크를 생성하는 데 사용되는가?

> `< a href="">`

<br>

- Which attribute of the link tag contains the URL location that you are trying to link to?
  - 링크 태그의 어떤 속성이 링크하려는 URL 위치를 포함하는가?

> `href`

<br>

- Which value of the target attribute makes the link open in a new tab or a new window?
  - target 속성의 어느 값으로 새 탭이나 새 창에서 링크를 열 수 있는가?

> `_blank`

<br>