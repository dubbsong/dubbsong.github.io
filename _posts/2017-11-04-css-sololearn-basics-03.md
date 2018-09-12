---
layout: post
title: "(Basics 03) CSS 규칙 & 선택자"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS Rules & Selectors

###### CSS 규칙 & 선택자

------

<br>

<br>

## CSS Syntax

###### CSS 문법

<br>

- CSS is composed of style rules that the browser interprets and then applies to the corresponding elements in your document.
  - CSS는 브라우저가 해석한 다음, 문서의 해당 element에 적용되는 style 규칙으로 구성된다.
- A style rule has three parts: `selector`, `property`, and `value`
  - style 규칙에는 세 가지 부분이 있다: `선택자`, `속성`, `값`

<br>

- For example, the headline color can be defined as:
  - 예를 들어, 제목 색상은 다음과 같이 정의할 수 있다.

```css
h1 { color: orange; }
```

[코드 실행 확인](https://code.sololearn.com/503/#css)

<br>

- Where:

![img](/assets/img/css-sololearn-basics-03-01.png)

<br>

- The selector points to the HTML element you want to style.
  - 선택자는 style을 지정할 HTML element를 가리킨다.

<br>

> The declaration block contains one or more declarations, separated by semicolons.
>
> 선언 블록은 세미콜론으로 구분된 하나 이상의 선언을 포함한다.

> Each declaration includes a property name and a value, separated by a colon.
>
> 각 선언에는 콜론으로 구분된 속성 이름과 값이 포함된다.

------

<br>

## Type Selectors

###### 타입 선택자

<br>

- The most common and easy to understand selectors are `type selectors`.
  - 가장 일반적이고 이해하기 쉬운 선택자는 `타입 선택자`이다.
- This selector targets element types on the page.
  - 이 선택자는 페이지의 element 타입을 겨냥한다.

<br>

- For example, to target all the paragraphs on the page:
  - 예를 들어, 페이지의 모든 토막글을 겨냥해보자.

```css
p {
   color: red;
   font-size: 130%;
}
```

[코드 실행 확인](https://code.sololearn.com/509/#css)

<br>

> A CSS declaration always ends with a semicolon, and declaration groups are surrounded by curly braces.
>
> CSS 선언은 항상 세미콜론으로 끝나며, 선언 그룹은 중괄호로 묶는다.

------

<br>

## id & class Selectors

###### id 선택자 & class 선택자

<br>

- `id selectors` allow you to style an HTML element that has an `id` attribute, regardless of their position in the document tree.
  - `id 선택자`를 사용하면 문서 트리에서의 위치에 관계없이, `id` 속성을 가지고 있는 HTML element의 style을 지정할 수 있다.

<br>

- The HTML:

```html
<div id="intro">
   <p>This paragraph is in the intro section. </p>
</div>
<p>This paragraph is not in the intro section. </p>
```

<br>

- The CSS:

```css
#intro {
   color: white;
   background-color: gray;
}
```

[코드 실행 확인](https://code.sololearn.com/504/#css)

<br>

> To select an element with a specific id, use a hash character, and then follow it with the id of the element.
>
> 특정 id가 있는 element를 선택하려면, hash 문자(#)를 사용한 다음, element의 id를 작성한다.

<br>

- Result:

![img](/assets/img/css-sololearn-basics-03-02.png)

<br>

- `class selectors` work in a similar way.
  - `class 선택자`도 유사한 방법으로 작동한다.
- The major difference is that IDs can only be applied once per page, while classes can be used as many times on a page as needed.
  - 가장 큰 차이점으로, ID는 페이지 당 한 번 만 적용할 수 있다.
  - 반면에 class는 한 페이지에서 필요에 따라 여러 번 사용할 수 있다.

<br>

- In the example below, both paragraphs having the class "first" will be affected by the CSS:
  - 아래 예제에서, "first" class를 가진 토막글은 모두 CSS의 영향을 받는다.

<br>

- The HTML:

```html
<div>
   <p class="first">This is a paragraph </p>
   <p>This is the second paragraph. </p>
</div>
<p class="first">This is not in the intro section </p>
<p>The second paragraph is not in the intro section. </p>
```

<br>

- The CSS:

```css
.first { font-size: 200%; }
```

<br>

> To select elements with a specific class, use a period character, followed by the name of the class.
>
> 특정 class가 있는 element를 선택하려면, 마침표를 사용한 다음, class 이름을 작성한다.

> Do `NOT` start a class or id name with a number!
>
> class나 id 이름을 숫자로 시작하지 마라.

------

<br>

## Descendant Selectors

###### 하위 선택자

<br>

- These selectors are used to select elements that are descendants of another element.
  - 이러한 선택자는 다른 element의 하위 element를 선택하는 데 사용된다.
- When selecting levels, you can select as many levels deep as you need to.
  - 레벨을 선택할 때, 필요한 만큼 많은 레벨을 선택할 수 있다.

<br>

- For example, to target only \<em> elements in the first paragraph of the "intro" section:
  - 예를 들어, "intro" 섹션의 첫 번째 토막글에서 \<em> element만 겨냥해보자.

<br>

- The HTML:

```html
<div id="intro">
   <p class="first">This is a <em>paragraph.</em></p>
   <p>This is the second paragraph. </p>
</div>
<p class="first">This is not in the intro section. </p>
<p>The second paragraph is not in the intro section. </p>
```

<br>

- The CSS:

```css
#intro .first em {
   color: pink;
   background-color: gray;
}
```

[코드 실행 확인](https://code.sololearn.com/506/#css)

<br>

- As a result, only the elements selected will be affected:
  - 결과적으로, 선택한 element만 영향을 받는다.

![img](/assets/img/css-sololearn-basics-03-03.png)

<br>

> The descendant selector matches all elements that are descendants of a specified element.
>
> 하위 선택자는 지정된 element의 모든 하위 element를 찾는다.

------

<br>

## QUIZ

- In the rule, the "selector":
  - 규칙에서 "selector"는 다음과 같다.

> `selects which element to style`
>
> style을 지정할 element를 선택한다

<br>

- Fill in the blanks to give yellow background color to the element with id="intro", and black text color to the class="mytext":
  - id="intro" element에 노란색 배경색을 지정하고, class="mytext"에 검은색 텍스트를 지정해라.

```css
#intro {
   background-color: yellow;
}

.mytext {
   color: black;
}
```

<br>

- Drag and drop from the options below to create a style rule for all paragraphs belonging to the element with id="test":
  - id="test" element에 속하는 모든 토막글에 대한 style 규칙을 생성해라.

```css
#test p {
   color: red;
}
```

<br>