---
layout: post
title: "(CSS3 Basics 09) Pseudo Element"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS Pseudo Elements

------

<br>

<br>

## Working with Pseudo Elements

###### pseudo element로 작업하기

<br>

- Pseudo elements are used to select specific parts of an element.
  - pseudo element는 element의 특정 부분을 선택하는 데 사용된다.
- There are five pseudo elements in CSS, each starting with a double colon (::).
  - CSS에는 5개의 pseudo element가 있으며, 각각 이중 콜론(::)으로 시작한다.

<br>

- `::first-line` - the first line of the text in a selector
  - selector 내 텍스트의 첫 번째 줄
- `::first-letter` - the first letter of the text in a selector
  - selector 내 텍스트의 첫 번째 글자
- `::selection` - selects the portion of an element that is selected by a user
  - 사용자가 선택한 element의 부분을 선택한다.
- `::before` - inserts some content before an element
  - element 앞에 content를 삽입한다.
- `::after` - inserts some content after an element
  - element 뒤에 content를 삽입한다.

<br>

- In the example below, the `::first-line` pseudo element is used to style the first line of our text:
  - 아래 예제에서 `::first-line` pseudo element는 텍스트의 첫 번째 줄 style을 지정하는 데 사용된다.

```css
p::first-line {
   color: #589432;
}
```

[코드 실행 확인](https://code.sololearn.com/593/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-09-01.png)

<br>

- The `::selection` pseudo element styles the selected text:
  - `::selection` pseudo element는 선택한 텍스트의 style을 지정한다.

```css
p::-moz-selection {
   background: #8bc34a;
   color: #fff;
}
```

[코드 실행 확인](https://code.sololearn.com/594/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-09-02.png)

<br>

> The `-moz-` prefix is used, as the `::selection` element is not supported by Mozilla yet.
>
> Mozilla에서는 `::selection` element가 아직 지원되지 않으므로, `-moz` 접두사가 사용된다.

<br>

<br>

- Using `::before` and `::after` pseudo elements allows us to add a wide variety of content to the page.
  - `::before`와 `::after` pseudo element를 사용하면 페이지에 대한 다양한 content를 추가할 수 있다.

<br>

- In the example below, the `::before` pseudo element is used to add an image before the list.
  - 아래 예제에서 `::before` pseudo element는 list 앞에 이미지를 추가하는 데 사용된다.

<br>

- HTML:

```html
<p>You can insert text, images, and other resources using<strong>:before</strong>pseudo element. </p>
<p>You can insert text, images, and other resources using<strong>:before</strong>pseudo element. </p>
<p>You can insert text, images, and other resources using<strong>:before</strong>pseudo element. </p>
```

<br>

- CSS:

```css
p::before {
   content: url("logo.jpg");
}
```

[코드 실행 확인](https://code.sololearn.com/595/#css)

<br>

> Note the `content` keyword in the syntax.
>
> 구문에서 `content` 키워드를 주의해라.

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-09-03.png)

<br>

> If you change the `::before` element to `::after` in the example above, the images will appear at the end of the list.
>
> 위 예제에서 `::before` element를 `::after`로 변경하면, 이미지가 list의 끝에 나타난다.

------

<br>

## QUIZ

- Which of the following is NOT a pseudo element in CSS?
  - 다음 중 CSS의 pseudo element가 아닌 것은 어느 것인가?

> [ ] ::before
>
> [ ] `::heading`
>
> [ ] ::selection
>
> [ ] ::first-line

<br>

- Add an image prior to the paragraph using a pseudo element.
  - pseudo element를 사용해서 토막글 앞에 이미지를 추가해라.

```css
p::before {
   content: url("img.jpg");
}
```

<br>