---
layout: post
title: "(Properties 07) background-repeat 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS background-repeat Property

###### background-repeat 속성

<br>

- The background-repeat property specifies how background images are repeated.
  - background-repeat 속성은 배경 이미지가 반복되는 방법을 지정한다.
- A background image can be repeated along the `horizontal axis`, the `vertical axis`, `both axes`, or `not repeated at all`.
  - 배경 이미지는 `가로 축`과 `세로 축`, `두 축`을 따라 반복되거나, `전혀 반복되지 않을 수 있다`.

<br>

- The `repeat-x` will repeat a background image only `horizontally`.
  - `repeat-x`는 `가로로`만 배경 이미지를 반복한다.

<br>

- CSS:

```css
body {
   background-image: url("css_logo.png");
   background-repeat: repeat-x;
}
```

[코드 실행 확인](https://code.sololearn.com/548/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-07-01.png)

<br>

- The `repeat-y` will repeat a background image only `vertically`.
  - `repeat-y`는 배경 이미지를 `세로로`만 반복한다.

<br>

- CSS:

```css
body {
   background-image: url("css_logo.png");
   background-repeat: repeat-y;
}
```

[코드 실행 확인](https://code.sololearn.com/549/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-07-02.png)

<br>

> If you want the image to be shown only `once`, use the `no-repeat` value.
>
> 이미지를 `한 번`만 표시하려면, `no-repeat` 값을 사용해라.

------

<br>

## Setting the Value to Inherit

###### 상속하도록 값 설정하기

<br>

- When you set the background-repeat property to `inherit`, it will take the same specified value as the property for the element's parent.
  - `상속`받기 위해 background-repeat 속성을 설정하면, element의 parent(부모)에 대한 속성과 동일한 지정된 값을 갖게 된다.

<br>

- For example, we set the body background-repeat only horizontally.
  - 예를 들어, body background-repeat은 가로로만 설정한다.
- If we set some paragraph background-repeat values to be inherited, they will take the same property value as the body element.
  - 일부 토막글 background-repeat 값을 상속받도록 설정하면, body element와 동일한 속성 값을 사용하게 된다.

<br>

- CSS:

```css
body {
   background-image: url("css_logo.png");
   backgournd-repeat: repeat-x;
}

p {
   background-image: url("css_logo.png");
   background-repeat: inherit;
   margin-top: 100px;
   padding: 40px;
}
```

[코드 실행 확인](https://code.sololearn.com/550/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-properties-07-03.png)

------

<br>

## QUIZ

- Fill in the blanks to make the background image repeat along the vertical axis:
  - 세로 축을 따라 배경 이미지가 반복되도록 만들어라.

```css
body {
   background-image: url("css_logo.png");
   background-repeat: repeat-y;
}
```

<br>

- The values that the background-repeat property accepts are: repeat, no-repeat, repeat-x, repeat-y and:
  - background-repeat 속성에서 허용하는 값은 repeat, no-repeat, repeat-x, repeat-y와 …이다.

> `inherit`

<br>
