---
layout: post
title: "(HTML5 06) audio element"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML5 audio Element

------

<br>

<br>

## Audio on the Web

###### 웹 상의 audio

<br>

- Before HTML5, there was no standard for playing audio files on a webpage.
  - HTML5 이전에는 웹페이지에서 audio 파일을 재생할 표준이 없었다.
- The HTML5 `<audio>` element specifies a standard for embedding audio in a webpage.
  - HTML5 `<audio>` element는 웹페이지에서 audio를 끼워 넣기 위한 표준을 지정한다.

<br>

- There are two different ways to specify the audio source file's URL.
  - audio source 파일의 URL을 지정하는 두 가지 다른 방법이 있다.
- The first uses the source attribute.
  - 첫 번째는 source 속성을 사용한다.

```html
<audio src="audio.mp3" controls>
   브라우저에서 지원하지 않는 audio element
</audio>
```

[코드 실행 확인](https://code.sololearn.com/40/#html)

<br>

- The second way uses the `<source>` element inside the `<audio>` element:
  - 두 번째 방법은 `<source>` element를 `<audio>` element 내에서 사용한다.

```html
<audio controls>
   <source src="audio.mp3" type="audio/mpeg">
   <source src="audio.ogg" type="audio/ogg">
</audio>
```

[코드 실행 확인](https://code.sololearn.com/41/#html)

<br>

> Multiple \<source> elements can be linked to different audio files.
>
> 여러 \<source> element를 서로 다른 audio 파일에 연결할 수 있다.

<br>

<br>

- The \<audio> element creates an audio player inside the browser.
  - \<audio> element는 브라우저 내에 audio player를 생성한다.

```html
<audio controls>
   <source src="audio.mp3" type="audio/mpeg">
   <source src="audio.ogg" type="audio/ogg">
   브라우저에서 지원하지 않는 audio element
</audio>
```

[코드 실행 확인](https://code.sololearn.com/42/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-html5-06-01.jpeg)

<br>

> The text between the \<audio> and \</audio> tags will display in browser that do not support the \<audio> element.
>
> \<audio> element를 지원하지 않는 브라우저에서는 \<audio> 와 \</audio> 태그 사이의 텍스트가 표시된다.

------

<br>

## Attributes of \<audio>

###### \<audio> 속성

<br>

#### controls

- Specifies that audio controls should be displayed (such as a play/pause button, etc).
  - audio control이 표시되도록 지정한다.
  - (재생/일시정지 버튼 등)

<br>

#### autoplay

- When this attribute is defined, audio starts playing as soon as it is ready, without asking for the visitor's permission.
  - 이 속성이 정의되면, 방문자의 동의 없이 audio가 준비되는 대로 재생을 시작한다.

```html
<audio controls autoplay>
```

[코드 실행 확인](https://code.sololearn.com/43/#html)

<br>

#### loop

- This attribute is used to have the audio replay every time it is finished.
  - 이 속성은 끝날 때마다 audio를 다시 재생하는 데 사용된다.

```html
<audio controls autoplay loop>
```

[코드 실행 확인](https://code.sololearn.com/44/#html)

<br>

> Currently, there are three supported file formats for the \<audio> element: `MP3`, `WAV`, and `OGG`.
>
> 현재 \<audio> element에는 `MP3`, `WAV`, `OGG`의 세 가지 지원되는 파일 형식이 있다.

------

<br>

## QUIZ

- Fill in the blanks to add an audio element:
  - audio element를 추가해라.

```html
<audio controls>
   <source src="test.ogg"
           type="audio/ogg">
</audio>
```

<br>

- The text in between the audio tags is:
  - audio 태그 사이의 텍스트는

> `for not supported browsers`
>
> 지원되지 않는 브라우저의 경우이다.

<br>

- Which of the following is not an attribute of the audio element?
  - 다음 중 audio element의 속성이 아닌 것은 무엇인가?

> [ ] controls
>
> [ ] `repeat`
>
> [ ] autoplay
>
> [ ] src

<br>