---
layout: post
title: "(HTML5 15) SVG vs. canvas"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML5 SVG vs. canvas

###### SVG vs. canvas

<br>

#### SVG

- Elements are part of the page's DOM (Document object model)
  - element는 페이지의 DOM(문서 객체 모델)에 포함된다.
- Drawing is done with vectors
  - 그리기는 벡터로 수행된다.
- Effects, such as animations are built in
  - 애니메이션과 같은 효과가 내장되어 있다.
- Based on standard XML syntax, which provides better accessibility
  - 더 나은 접근성을 제공하는 표준 XML 구문을 기반으로 한다.
- Resolution independent
  - 독립적인 해상도.
- Support for event handlers
  - 이벤트 핸들러 지원.
- Not suited for game applications
  - 게임 애플리케이션에는 적합하지 않다.
- Best suited for applications with large rendering areas (for example, Google Maps)
  - 대형 렌더링 영역이 있는 애플리케이션에 가장 적합하다.
  - (예: Google Maps)

<br>

#### canvas

- Elements are drawn programmatically
  - element는 프로그래밍 방식으로 그려진다.
- Drawing is done with pixels
  - 그리기는 픽셀로 수행된다.
- Animations are not built in
  - 애니메이션은 내장되어 있지 않다.
- High perfomance for pixels-based drawing operations
  - 픽셀 기반 그리기 작업을 위한 고성능이다.
- Resolution dependent
  - 해상도에 따라 다르다.
- No support for event handlers
  - 이벤트 핸들러에 대한 지원이 없다.
- You can save the resulting image as .png or .jpg
  - 결과 이미지를 .png 또는 .jpg로 저장할 수 있다.
- Well suited for graphic-intensive games
  - 그래픽 집약적인 게임에 적합하다.

<br>

> You can actually use both SVG and canvas on the same page, if needed.
>
> 필요한 경우, 실제로 동일한 페이지에서 SVG와 canvas를 모두 사용할 수 있다.

> However, you cannot just draw SVG onto a canvas, or vice-versa.
>
> 하지만 SVG를 canvas에 그리거나, 그 반대로 할 수는 없다.

------

<br>

## QUIZ

- Which of the following statements are true?
  - 어떤 것이 true인가?

> [ ] `SVG has better accessibility`
>
> [ ] SVG needs scripts to draw elements
>
> [ ] Canvas contains built-in animations.
>
> [ ] `In canvas, drawing is done with pixels`

<br>