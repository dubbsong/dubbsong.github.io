---
layout: post
title: "SoloLearn HTML 번역 - 06. The audio Element (HTML5)"
categories: dev
tags: html
---

## Audio on the Web

###### 웹에서의 오디오

<br>

- Before HTML5, there was no standard for playing audio files on a web page.
  - HTML5 이전에는 웹 페이지에서 오디오 파일을 재생할 표준이 없었다.
- The HTML5 `<audio>` element specifies a standard for embedding audio in a web page.
  - HTML5 `<audio>` element는 웹 페이지에 오디오를 삽입하는 표준을 지정한다.

<br>

- There are two different ways to specify the audio source file's URL.
  - 오디오 소스 파일의 URL을 지정하는 두 가지 방법이 있다.
- The first uses the source attribute:
  - 첫 번째는 source 속성을 사용한다.

```html
<audio src="audio.mp3" controls>
	Audio element not supported by your browser
</audio>
```

<br>

- The second way uses the `<source>` element inside the `<audio>` element:
  - 두 번째 방법은 `<source>` element를 `<audio>` element 내부에서 사용한다.

```html
<audio controls>
	<source src="audio.mp3" type="audio/mpeg">
   <source src="audio.ogg" type="audio/ogg">
</audio>
```

<br>

> Multiple `<source>` elements can be linked to different audio files.
>
> 여러 `<source>` element를 다른 오디오 파일에 연결할 수 있다.

> The browser will use the first recognized format.
>
> 브라우저는 인식된 첫 번째 format을 사용한다.

------

<br>

## Audio on the Web 02

- The `<audio>` element creates an audio player inside the browser.
  - `<audio>` element는 브라우저 내에 오디오 플레이어를 생성한다.

```html
<audio controls>
	<source src="audio.mp3" type="audio/mpeg">
   <source src="audio.ogg" type="audio/ogg">
   Audio element not supported by your browser.
</audio>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-html5-06-01.jpeg)

<br>

> The text between the `<audio>` and `</audio>` tags will display in browsers that do not support the `<audio>` element.
>
> `<audio>` element를 지원하지 않는 브라우저에서는 `<audio>` 태그와 `</audio>` 태그 사이의 텍스트가 표시된다.

------

<br>

## Attributes of \<audio>

###### \<audio> 속성

<br>

#### controls

- Specifies that audio controls should be displayed (such as a play/pause button, etc.)
  - 오디오 컨트롤이 표시되도록 지정한다. (재생/일시정지 버튼처럼)

<br>

#### autoplay

- When this attribute is defined, audio starts playing as soon as it is ready, without asking for the visitor's permission.
  - 이 속성이 정의되면, 오디오는 방문자의 허가에 대한 물음 없이 준비가 되는 대로 재생을 시작한다.

```html
<audio controls autoplay>
```

<br>

#### loop

- This attribute is used to have the audio replay every time it is finished.
  - 이 속성은 끝날 때마다 오디오를 다시 재생하는 데 사용된다.

```html
<audio controls autoplay loop>
```

<br>

> Currently, there are three supported file formats for the `<audio>` element: MP3, WAV, and OGG.
>
> 현재 `<audio>` element에는 지원되는 세 가지 파일 형식이 있다: MP3, WAV, OGG.

------

<br>

## QUIZ

- Fill in the blanks to add an audio element:
  - 빈칸을 채워서 오디오 element를 추가해라.

```html
<audio controls>
	<source src="test.ogg" type="audio/ogg">
</audio>
```

<br>

- The text in between the audio tags is:
  - 오디오 태그 사이의 텍스트는 다음과 같다.

> [ ] for supporting multiple audio type
>
> [ ] ignored
>
> [x] `for not supported browsers`

<br>

- Which of the following is not an attribute of the audio element?
  - 다음 중 audio element의 속성이 아닌 것은 어떤 것인가?

> [ ] autoplay
>
> [ ] controls
>
> [x] `repeat`
>
> [ ] src

<br>