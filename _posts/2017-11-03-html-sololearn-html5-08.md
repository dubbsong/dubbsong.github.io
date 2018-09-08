---
layout: post
title: "08. The progress Element (HTML5)"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML progress element

###### HTML 진행 표시 element

------

<br>

<br>

## Progress Bar

###### 진행 표시 줄

<br>

- The `<progress>` element provides the ability to create progress bars on the web.
  - `<progress>` element는 웹에서 진행 표시 줄을 만드는 기능을 제공한다.
  - `<progress>`: Represents the progress of a task, 작업 진행 상황을 나타낸다.
- The progress element can be used within headings, paragraphs, or anywhere else in the body.
  - progress element는 heading, paragraph, body의 다른 곳에서 사용될 수 있다.

<br>

#### Progress Element Attributes

- `Value`: Specifies how much of the task has been completed.
  - 완료된 작업의 양을 지정한다.
- `Max`: Specifies how much work the task requires in total.
  - 작업에 필요한 총 작업량을 지정한다.

<br>

- Example:

```html
Status: <progress min="0" max="100" value="35">
</progress>
```

<br>

- Result:

![sololearn img](/aseets/img/sololearn-html-html5-08-01.jpeg)

<br>

> Use the `<progress>` tag in conjunction with JavaScript to dynamically display a task's progress.
>
> JavaScript와 함께 `<progress>` 태그를 사용해서 작업 진행 상황을 동적으로 표시한다.

------

<br>

## QUIZ

- Define a progress bar that shows 63 percent of progress:
  - 진행률 63%를 표시하는 진행 표시 줄을 정의해라.

```html
<progress min="0" max="100" value="63">
</progress>
```

<br>