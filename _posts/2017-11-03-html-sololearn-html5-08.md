---
layout: post
title: "(HTML5 08) progress element"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML5 progress Element

------

<br>

<br>

## Progress Bar

###### 진행 표시 줄

<br>

- The `<progress>` element provides the ability to create progress bars on the web.
  - `<progress>` element는 웹에서 진행 표시 줄을 생성하는 기능을 제공한다.
- The progress element can be used within headings, paragraphs, or anywhere else in the body.
  - progress element는 제목, 토막글, body의 다른 곳에서 사용될 수 있다.

<br>

#### Progress Element Attributes

###### progress element 속성

<br>

- `value`: Specifies how much of the task has been completed.
  - 완료된 작업의 양을 지정한다.
- `max`: Specifies how much work the task requires in total.
  - 작업에 필요한 작업량의 합계를 지정한다.

<br>

- Example:

```html
Status: <progress min="0" max="100" value="35"></progress>
```

[코드 실행 확인](https://code.sololearn.com/47/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-html5-08-01.jpeg)

<br>

> Use the \<progress> tag in conjunction with JavaScript to dynamically display a task's progress.
>
> JavaScript와 함께 \<progress> 태그를 사용해서 작업 진행을 동적으로 표시한다.

------

<br>

## QUIZ

- Define a progress bar that shows 63 percent of progress:
  - 진행률의 63퍼센트를 보여주는 진행 표시 줄을 정의해라.

```html
<progress
          min="0"
          max="100"
          value="63">
</progress>
```

<br>