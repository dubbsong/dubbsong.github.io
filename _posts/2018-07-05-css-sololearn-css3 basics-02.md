---
layout: post
title: "(CSS3 Basics 02) vendor 접두사"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS Vendor Prefixes

###### vendor 접두사

<br>

- CSS vendor prefixes or CSS browser prefixes are a way for browser makers to add support for new CSS features during periods of testing and experimentation.
  - CSS vendor 접두사 또는 CSS 브라우저 접두사는 브라우저 제작자가 테스트와 실험 기간 동안 새로운 CSS 기능에 대한 지원을 추가하는 방법이다.
- Browser prefixes are used to add new features that may not be part of the final and formal CSS specification.
  - 브라우저 접두사는 새로운 기능을 추가하는 데 사용된다.
  - (최종 및 공식 CSS 명세의 일부분이 아닌)

<br>

- For example, the prefix for Safari and Chrome is `-webkit`.
  - 예를 들어, Safari와 Chrome의 접두사는 `-webkit`이다.
- The `border-radius` property is currently supported in Chrome, Safari, and Mozilla, as long as it is accompanied by the browser prefix.
  - `border-radius` 속성은 현재 Chrome, Safari, Mozilla에서 지원된다.
  - (브라우저 접두사가 붙어있는 한)
- To specify the `border-radius` in Chrome and Safari, the following syntax is used:
  - Chrome과 Safari에서 `border-radius`를 지정하기 위해 다음 구문이 사용된다.

```css
-webkit-border-radius: 24px;
```

[코드 실행 확인](https://code.sololearn.com/579/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-02-01.png)

<br>

- The prefix is added to the property to make it work in the unsupported browsers.
  - 지원되지 않는 브라우저에서 작동하게 하려면, 접두사가 속성에 추가된다.
- So, you might end up with multiple definitions of the same property, each with the specific browser prefix.
  - 따라서, 동일한 속성의 여러 정의로 끝날 수 있다.
  - 각각의 속성에는 특정 브라우저 접두사가 붙는다.

<br>

> While most browsers today will work without prefixes, it is essential to know these for backwards capability and understanding older codes.
>
> 오늘날 대부분의 브라우저는 접두사 없이 작동되지만, 이전 기능과 코드를 이해하는 것이 중요하다.

------

<br>

## Browser Prefixes

###### 브라우저 접두사

<br>

- Here is the list of vendor prefixes for each browser.
  - 다음은 각 브라우저의 vendor 접두사 list이다.

![img](/assets/img/css-sololearn-css3 basics-02-02.png)

<br>

> It might feel annoying and repetitive to have to write the properties two to five times to get them to work in all browsers, but it's temporary.
>
> 모든 브라우저에서 작동하도록 2~5번 속성을 작성해야 하는 것은 성가시고 반복적이지만, 일시적이다.

> As browsers improve, they add support for the standards based version of the properties, and you can remove the prefixed versions.
>
> 브라우저가 향상됨에 따라, 표준 기반 버전의 속성에 대한 지원이 추가되고, 접두사가 붙은 버전을 제거할 수 있다.

------

<br>

## QUIZ

- Fill in the blanks to add the right prefix for Google Chrome.
  - Google Chrome에 대한 접두사를 추가해라.

> `-webkit-border-radius: 15px;`

<br>

- Drag and drop from the options below to support border-radius in Mozilla Firefox, as well as in Webkit-based browsers.
  - Webkit 기반의 브라우저와 마찬가지로, Mozilla Firefox에서 border-radius를 지원해라.

```css
.test {
   -webkit-border-radius: 8px;
   -moz-border-radius: 8px;
}
```

<br>