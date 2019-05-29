---
layout: post
title: "(HTML5 07) video element"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML5 video Element

------

<br>

<br>

## videos in HTML

###### HTML의 video

<br>

- The video element is similar to the audio element.
  - video element는 audio element와 유사하다.
- You can specify the video source URL using an attribute in a video element, or using source elements inside the video element.
  - video element의 속성을 사용하거나, video element 내의 source element를 사용해서 video source URL을 지정할 수 있다.

```html
<video controls>
   <source src="video.mp4" type="video/mp4">
   <source src="video.ogg" type="video/ogg">
   브라우저에서 video를 지원하지 않는다.
</video>
```

[코드 실행 확인](https://code.sololearn.com/45/#html)

<br>

> Another aspect that the audio and video elements have in common is that the major browsers do not all support the same file types.
>
> audio와 video element가 공통적으로 가지고 있는 또 다른 측면은, 주요 브라우저가 모두 동일한 파일 type을 지원하지 않는다는 것이다.

> If the browser does not support the first video type, it will try the next one.
>
> 브라우저가 첫 번째 video type을 지원하지 않으면, 다음 것을 시도한다.

------

<br>

## Attributes of \<video>

###### \<vidoe>의 속성

<br>

- Another aspect shared by both the audio and the video elements is that each has `controls`, `autoplay`, and `loop` attributes.
  - audio와 video element가 공유하는 또 다른 측면은, 각각 `controls`, `autoplay`, `loop` 속성이 있다는 것이다.

<br>

- In this example, the video will replay after it finishes playing:
  - 아래 예제에서는, 재생이 끝나면 video가 다시 재생된다.

```html
<video controls autoplay loop>
   <source src="video.mp4" type="video/mp4">
   <source src="video.ogg" type="video/ogg">
   브라우저에서 video를 지원하지 않는다.
</video>
```

[코드 실행 확인](https://code.sololearn.com/46/#html)

<br>

> Currently, there are three supported video formats for the \<video> element: `MP4`, `WebM`, and `OGG`.
>
> 현재 \<video> element에는 `MP4`, `WebM`, `OGG`의 세 가지 지원되는 video 형식이 있다.

------

<br>