---
layout: post
title: "SoloLearn 번역 - 03. CSS Syntax (The Basics)"
categories: dev
tags: css
---

## CSS Syntax

- CSS is composed of style rules that the browser interprets and then applies to the corresponding elements in your document.
  - CSS는 브라우저가 해석한 다음 문서의 해당 element에 적용되는 스타일 규칙으로 구성된다.
- A style rule has three parts: **selector**, **property**, and **value**.
  - 스타일 규칙에는 세 가지 부분이 있다: **selector**, **property**, **value**.

<br>

- For example, the headline color can be defined as:
  - 예를 들어, 헤드라인 색상은 다음과 같이 정의될 수 있다.

```css
h1 {color: orange;}
```

<br>

- Where:

![SoloLearn img](/assets/img/sololearn-css-the basics-03-01.png)

<br>

- The selector points to the HTML element you want to style.
  - selector는 스타일을 지정할 HTML element를 가리킨다.

<br>

> The declaration block contains one or more declarations, separated semicolons.
>
> 선언 블록은 세미콜론으로 구분된 하나 이상의 선언을 포함한다.

> Each declaration includes a property name and a value, separated by a colon.
>
> 각 선언에는 콜론으로 구분된 속성 이름과 값이 포함된다.

------

<br>

## Type Selectors

- The most common and easy to understand selectors are **type selectors**.
  - 가장 일반적이고 이해하기 쉬운 selector는 **type selector**이다.
- This selector targets element types on the page.
  - selector는 페이지의 element 타입을 대상으로 한다.

<br>

- For example, to target all the paragraphs on the page:
  - 예를 들어, 페이지의 모든 단락을 지정하려면 다음과 같이 해라.

```css
p {
   color: red;
   font-size: 130%;
}
```

<br>

> A CSS declaration always ends with a semicolon, and declaration groups are surrounded by curly braces.
>
> CSS 선언은 항상 세미콜론으로 끝나며, 선언 그룹은 중괄호로 묶는다.

------

<br>

## id and class Selectors

- **id selectors** allow you to style an HTML element that has an **id** attribute, regardless of their position in the document tree.
  - **id selectors**를 사용하면 문서 트리에서의 위치에 상관없이 **id** 속성이 있는 HTML element의 스타일을 지정할 수 있다.
- Here is an example of an id selector.
  - 다음은 id selector의 예제이다.

<br>

- The HTML:

```html
<div id="intro">
   <p>This paragraph is in the intro section.</p>
</div>
<p>This paragraph is not in the intro section.</p>
```

<br>

- The CSS:

```css
#intro {
   color: white;
   background-color: gray;
}
```

<br>

> To select an element with a specific id, use a hash character, and then follow it with the id of the element.
>
> 특정 id가 있는 element를 선택하려면, 해시 문자를 사용한 다음, element의 id를 따라야 한다.

<br>

- Result:

![SoloLearn img](/assets/img/sololearn-css-the basics-03-02.png)

<br>

- **Class selectors** work in a similar way.
  - **class selectors**도 비슷한 방식으로 작동한다.
- The major difference is that IDs can only be applied once per page, while classes can be used as many times on a page as needed.
  - 가장 큰 차이점은 페이지 당 한 번만 ID를 적용할 수 있고, 필에요 따라 페이지에서 여러 번 사용할 수 있다는 것이다.

<br>

- In the example below, both paragraphs having the class "first" will be affected by the CSS:
  - 아래 예제에서, class "first"를 가진 두 단락 모두 CSS의 영향을 받는다.

<br>

- The HTML:

```html
<div>
   <p class="first">This is a paragraph</p>
   <p>This is the second paragraph</p>
</div>
<p class="first">This is not in the intro section</p>
<p>The second paragraph is not in the intro section.</p>
```

<br>

- The CSS:

```css
.first {font-size: 200%;}
```

<br>

> To select elements with a specific class, use a period character, followed by the name of the class.
>
> 특정 class가 있는 element를 선택하려면, 마침표를 사용하고, class의 이름이 뒤를 따른다.

> Do **NOT** start a class or id name with a number!
>
> class나 id 이름을 숫자로 시작하지 마라!

<br>

------

<br>

## Descendant Selectors

- These selectors are used to select elements that are descendants of another element.
  - 이 selector들은 다른 element의 하위 element를 선택하는 데 사용된다.
- When selecting levels, you can select as many levels deeps as you need to.
  - level을 선택할 때, 필요한 만큼 많은 level을 선택할 수 있다.

<br>

- For example, to target only \<em> elements in the first paragraph of the "intro" section:
  - 예를 들어, "intro" 섹션의 첫 번째 단락에서 \<em> element만 타게팅하려면 다음과 같이 해라.

<br>

- The HTML:

```html
<div id="intro">
   <p class="first">This is a \<em>paragraph.</em></p>
   <p>This is the second paragraph.</p>
</div>
<p class="first">This is not in the intro section.</p>
<p>The second paragraph is not in the intro section.</p>
```

<br>

- The CSS:

```css
#intro .first em {
   color: pink;
   background-color: gray;
}
```

<br>

- As a result, only the elements selected will be affected:
  - 결과적으로, 선택한 element만 영향을 받는다.

![SoloLearn img](/assets/img/sololearn-css-the basics-03-03.png)

------

<br>

## QUIZ

- In the rule, the "selector":
  - serves as a property
  - **selects which element to style**
  - allows to substitute the selected attribute

<br>

- Rearrange the code to create a valid CSS style rule:

```css
p {
   color: blue;
}
```

<br>

- Fill in the blanks to give yellow background color to the element with id="intro", and black text color to the class="mytext":

```html
#intro {
	background-color: yellow;
}

.mytext {
	color: black;
}
```

<br>

- Drag and drop from the options below to create a style rule for all paragraphs belonging to the element with id="test":

```css
#test p {
   color: red;
}
```

<br>