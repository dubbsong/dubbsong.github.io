---
layout: post
title: "SoloLearn HTML 번역 - 07. The video Element (HTML5)"
categories: dev
tags: html
---

## Videos in HTML

###### HTML video

<br>

- The video element is similar to the audio element.
  - video element는 audio element와 유사하다.
- You can specify the video source URL using an attribute in a video element, or using source elements inside the video element.
  - video element의 속성을 사용하거나, video element 내의 source element를 사용해서, video source URL을 지정할 수 있다.

```html
<video controls>
	<source src="video.mp4" type="video/mp4">
   <source src="video.ogg" type="video/ogg">
   Video is not supported by your browser
</video>
```

<br>

> Another aspect that the audio and video elements have in common is that the major browsers do not all support the same file types.
>
> audio와 video element가 공통적으로 가지고 있는 또 다른 측면은, 주요 브라우저가 모두 동일한 파일 type을 지원하지 않는다는 것이다.

> If the browser does not support the first video type, it will try the next one.
>
> 브라우저가 첫 번째 video type을 지원하지 않으면, 다음 video type을 시도한다.

------

<br>

## Attributes of \<video>

###### \<video> 속성

<br>

- Another aspect shared by both the audio and the video elements is that each has `controls`, `autoplay` and `loop` attributes.
  - audio와 video element가 공유하는 또 다른 측면은, 각각 `controls`, `autoplay`, `loop` 속성이 있다는 것이다.

<br>

- In this example, the video will replay after it finishes playing:
  - 이 예제에서, 재생이 끝나면 video가 다시 재생된다.

```html
<video controls autoplay loop>
	<source src="video.mp4" type="video/mp4">
   <source src="video.ogg" type="video/ogg">
   Video is not supported by your browser
</video>
```

<br>

> Currently, there are three supported video formats for the `<video>` element: MP4, WebM, and OGG.
>
> 현재 `<video>` element에는 지원되는 세 가지 video 형식이 있다: MP4, WebM, OGG.

------

<br>

## QUIZ

- Fill in the blanks to create a video element:
  - video element를 만들기 위해 빈칸을 채워라.

```html
<video controls>
	<source src="video.mp4" type="video/mp4"/>
   <source src="video.ogg" type="video/ogg"/>
   Video not supported
</video>
```

<br>

- Rearrange the code to create a valid video tag that will attempt to play the mp4 file first.
  - 먼저 mp4 파일을 재생하려고 하는 유효한 video 태그를 만들기 위해서 코드를 재정렬해라.

> \<video controls>
>
> \<source src="a.mp4" type="video/mp4">
>
> \<source src="a.ogg" type="video/ogg">
>
> Video is not supported
>
> \</video>

<br>