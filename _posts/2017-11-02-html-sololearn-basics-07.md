---
layout: post
title: "07. Images (Basics)"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML Images

###### HTML 이미지

------

<br>

<br>

## The \<img> Tag

###### \<img> 태그

<br>

- The `<img>` tag is used to insert an image.
  - `<img>` 태그는 이미지를 삽입하는 데 사용된다.
- It contains only attributes, and does not have a closing tag.
  - 속성만 포함하고, 닫는 태그가 없다.

<br>

- The image's URL (address) can be defined using the `src` attribute.
  - 이미지의 URL(주소)은 `src` 속성을 사용해서 정의할 수 있다.

<br>

- The HTML image syntax looks like this:
  - HTML 이미지 문법은 다음과 같다.

```html
<img src="image.jpg" />
```

------

<br>

## Image Location

###### 이미지 위치

<br>

- You need to put in the `image location` for the src attribute that is between the quotation marks.
  - 따옴표 사이에 있는 src 속성에 `이미지 위치`를 입력해야 한다.

<br>

- For example, if you have a photo named "tree.jpg" in the same folder as the HTML file, your code should look like this:
  - 예를 들어, HTML 파일과 동일한 폴더에 "tree.jpg"라는 이름의 사진이 있는 경우, 코드는 다음과 같다.

```html
<html>
   <head>
      <title>first page</title>
   </head>
   <body>
      <img src="tree.jpg" alt="" />
   </body>
</html>
```

<br>

> In case the image cannot be displayed, the alt attribute specifies an alternate text that describes the image in words.
>
> 이미지를 표시할 수 없는 경우, alt 속성은 이미지를 단어로 설명하는 대체 텍스트를 지정한다.

> The alt attribute is `required`.
>
> alt 속성은 `필수`다.

------

<br>

## Image Resizing

###### 이미지 사이즈 조절

<br>

- To define the image size, use the width and height attributes.
  - 이미지 사이즈를 정의하려면, width와 height 속성을 사용해라.
- The value can be specified in `pixels` or as a `percentage`:
  - 값은 `pixels` 또는 `percentage`로 지정할 수 있다.

```html
<html>
   <head>
      <title>first page</title>
   </head>
   <body>
      <img src="tree.jpg" height="150px" width="150px" alt="" />
      <!-- or -->
      <img src="tree.jpg" height="50%" width="50%" alt="" />
   </body>
</html>
```

<br>

> Loading images takes time.
>
> 이미지 로딩에는 시간이 걸린다.

> Using large images can slow down your page, so use them with care.
>
> 큰 이미지를 사용하면 페이지가 느려질 수 있으므로, 주의해서 사용해라.

------

<br>

## Image Border

###### 이미지 테두리

<br>

- By default, an image has no borders.
  - 기본적으로, 이미지에는 테두리가 없다.
- Use the border attribute within the image tag to create a border around the image.
  - 이미지 태그 내의 border 속성을 사용해서 이미지 주위에 테두리를 만든다.

```html
<img src="tree.jpg" height="150px" width="150px" border="1px" alt="" />
```

<br>

> By default, Internet Explorer 9, and its earlier versions, display a border around an image unless a border attribute is defined.
>
> 기본적으로, Internet Explorer 9과 이전 버전에서는, border 속성이 정의되어 있지 않으면 이미지 주위에 테두리가 표시된다.

------

<br>

## QUIZ

- What tag should be used to add an image?
  - 이미지를 추가할 때 어떤 태그를 사용해야 하는가?

> `<img />`

<br>

- What attribute should be used to add an image URL?
  - 이미지 URL을 추가할 때 어떤 속성을 사용해야 하는가?

> [ ] location
>
> [ ] address
>
> [ ] `src`
>
> [ ] url

<br>

- What two attributes can be used to resize images inside HTML code?
  - HTML 코드에서 이미지 사이즈를 조절하는 데 사용할 수 있는 두 개의 속성은 무엇인가?
- Select all that apply
  - 해당되는 모든 것을 골라라.

> [ ] size
>
> [ ] quantity
>
> [ ] `height`
>
> [ ] `width`

<br>

- Fill in the blank:
  - 빈칸을 채워라.

```html
<img src="tree.jpg" alt"" />
```

<br>