---
layout: post
title: "18. HTML5 Forms, Part 2 (HTML5)"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

## Creating a Search Box

###### 검색창 만들기

<br>

- The new `search` input type can be used to create a search box:
  - 새로운 `search` input type을 사용해서 검색창을 만들 수 있다.

```html
<input id="mysearch" name="searchitem" type="search" />
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-html5-18-01.png)

------

<br>

## Search Options

###### 검색 옵션

<br>

- The `<datalist>` tag can be used to define a list of pre-defined options for the search field:
  - `<datalist>` 태그는 검색 field에 대해서 사전 정의된 옵션을 정의하는 데 사용할 수 있다.
  - `<datalist>`: Specifies a list of pre-defined options for input controls

```html
<input id="car" type="text" list="colors" />
<datalist id="colors">
   <option value="Red">
   <option value="Green">
   <option value="Yellow">
</datalist>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-html5-18-02.jpeg)

<br>

- `<option>` defines the options in a drop-down list for the user to select.
  - `<option>`은 사용자가 선택할 수 있는 drop-down list의 옵션을 정의한다.

<br>

> The ID of the datalist element must match with the list attribute of the input box.
>
> datalist element의 ID는 input box의 list 속성과 일치해야 한다.

------

<br>

## Creating More Fields

###### 추가 field 만들기

<br>

- Some other new input types include `email`, `url`, and `tel`:
  - 다른 새로운 input type은 `email`, `url`, `tel`을 포함한다.

```html
<input id="email" name="email" type="email" placeholder="example@example.com" />
<br />
<input id="url" name="url" type="url" placeholder="example.com" />
<br />
<input id="tel" name="tel" type="tel" placeholder="555.555.1211" />
```

<br>

- These are especially useful when opening a page on a modern mobile device, which recognizes the input types and opens a corresponding keyboard matching the field's type:
  - 이러한 것은 input type을 인식하고, field type와 일치하는 키보드를 여는 최신 모바일 장치에서 페이지를 열 때 특히 유용하다.

![sololearn img](/assets/img/sololearn-html-html5-18-03.png)

<br>

> These new types make it easier to structure and validate HTML forms.
>
> 이러한 새로운 type을 사용하면, HTML form을 쉽게 구조화하거나 유효성 검사를 할 수 있다.

------

<br>

## QUIZ

- Fill in the blank to create a Search Box:
  - 빈칸을 채워서 검색창을 만들어라.

```html
<input type="search" />
```

<br>

- Fill in the blanks to associate the input with the datalist:
  - 빈칸을 채워서 input을 datalist에 연결해라.

```html
<form>
   <input type="text" name="color" list="colors" />
   <datalist id="colors">
   	<option value="Red">
      <option value="Blue">
      <option value="Green">
   </datalist>
</form>
```



<br>

- Which of the following is not a supported type for the input tag?
  - input 태그에 지원되는 type이 아닌 것은 어떤 것인가?

> [ ] tel
>
> [ ] `planet`
>
> [ ] submit
>
> [ ] url

<br>
