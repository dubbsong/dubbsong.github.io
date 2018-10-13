---
layout: post
title: "(CSS3 Basics 10) word-wrap 속성"
categories: css
---

###### [SoloLearn](https://www.sololearn.com/) CSS 번역

<br>

# CSS word-wrap Property

###### word-wrap 속성

<br>

- The word-wrap property allows long words to be broken and wrapped into the next line.
  - word-wrap 속성을 사용하면 긴 단어가 깨져서 다음 줄로 감싸진다.

- It takes two values: `normal` and `break-word`.
  - 이 속성은 `normal`과 `break-word` 두 개의 값을 가진다.

<br>

- In the example below, the word-wrap property is set to `normal`.
  - 아래 예제에서 word-wrap 속성은 `normal`로 설정된다.

<br>

- CSS:

```css
p {
   width: 210px;
   height: 100px;
   border: 1px solid #000000;
   word-wrap: normal;
}
```

[코드 실행 확인](https://code.sololearn.com/596/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-10-01.png)

<br>

- Now let's see what happens when we use this same example and set the word-wrap property to break-word:
  - word-wrap 속성을 break-word로 설정할 때 어떤 일이 일어나는지 살펴보자.

```css
p {
   width: 210px;
   height: 100px;
   border: 1px solid #000000;
   word-wrap: break-word;
}
```

[코드 실행 확인](https://code.sololearn.com/597/#css)

<br>

- Result:

![img](/assets/img/css-sololearn-css3 basics-10-02.png)

<br>

> When the word-wrap property is set to `break-word`, the browser breaks a word when it is too long to fit within its container.
>
> word-wrap 속성이 `break-word`로 설정되면, 브라우저가 너무 길어서 해당 컨테이너에 맞지 않을 때 단어가 깨진다.

------

<br>

## QUIZ

- Fill in the blanks to fit the text into the paragraph:
  - 텍스트를 토막글에 맞춰라.

```css
p {
   width: 300px;
   word-wrap: break-word;
}
```

<br>