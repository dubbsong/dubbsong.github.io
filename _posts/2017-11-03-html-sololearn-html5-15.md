---
layout: post
title: "15. SVG vs. Canvas (HTML5)"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML Canvas vs. SVG

#### Canvas

- Elements are drawn programmatically
  - element는 프로그래밍 방식으로 그려진다.
- Drawing is done with pixels
  - 드로잉은 픽셀로 수행된다.
- Animations are not built in
  - 애니메이션은 내장되어 있지 않다.
- High performance for pixels-based drawing operations
  - 픽셀 기반 드로잉 작업을 위한 고성능이다.
- Resolution dependent
  - 해상도에 따라 다르다.
- No support for event handlers
  - 이벤트 핸들러에 대한 지원이 없다.
- You can save the resulting image as .png or .jpg
  - 결과 이미지를 .png 또는 .jpg로 저장할 수 있다.
- Well suited for graphic-intensive games
  - 그래픽 집중적인 게임에 적합하다.

<br>

#### SVG

- Elements are part of the page's DOM (Document object model)
  - element는 페이지의 DOM(문서 객체 모델)에 포함된다.
- Drawing is done with vectors
  - 드로잉은 벡터로 수행된다.
- Effects, such as animations are built in
  - 애니메이션과 같은 효과가 내장되어 있다.
- Based on standard XML syntax, which provides better accessibility
  - 더 나은 접근성을 제공하는 표준 XML 구문을 기반으로 한다.
- Resolution independent
  - 해상도에 독립적이다.
- Support for event handlers
  - 이벤트 핸들러를 지원한다.
- Not suited for game applications
  - 게임 애플리케이션에는 적합하지 않다.
- Best suited for applications with large rendering areas (for example, Google Maps)
  - 대형 렌더링 영역이 있는 애플리케이션(예를 들어, 구글 맵)에 가장 적합하다.

<br>

> You can actually use both SVG and canvas on the same page, if needed.
>
> 필요한 경우, 같은 페이지에서 SVG와 canvas를 모두 사용할 수 있다.

> However, you cannot just draw SVG onto a canvas, or vice-versa.
>
> 하지만, SVG를 canvas에 그릴 수 없고, 그 반대로도 할 수 없다.

------

<br>

## QUIZ

- Which of the following statements are true?
  - 다음 표현들 중 사실은 어떤 것인가?
  - Select all that apply

> [ ] `SVG has better accessibility.`
>
> [ ] `In Canvas, drawing is done with pixels.`
>
> [ ] SVG needs scripts to draw elements.
>
> [ ] Canvas contains built-in animations.

<br>