---
layout: post
title: "17. HTML5 Forms, Part 1 (HTML5)"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML5 Forms

- HTML5 brings many features and improvements to web form creation.
  - HTML5는 웹 form 제작에 많은 기능과 개선을 제공한다.
- There are new attributes and input types that were introduced to help create better experiences for web users.
  - 웹 사용자에게 더 나은 경험을 제공하기 위해 도입된 새로운 속성과 input type이 있다.

<br>

- Form creation is done in HTML5 the same way as it was in HTML4:
  - form 작성은 HTML5에서 HTML4와 동일한 방식으로 수행된다.

```html
<form>
   <label>Your name: </label>
   <input id="user" name="username" type="text" />
</form>
```

------

<br>

## New Attributes

###### 새로운 속성

<br>

- HTML5 has introduced a new attribute called `placeholder`.
  - HTML5는 `placeholder`라는 새로운 속성을 도입했다.
- On `<input>` and `<textarea>` elements, this attribute provides a hint to the user of what information can be entered into the field.
  - `<input>`과 `<textarea>` element에서 이 속성은 field에 입력할 수 있는 정보의 힌트를 사용자에게 제공한다.

```html
<form>
   <label for="email">Your e-mail address: </label>
   <input type="text" name="email" placeholder="email@example.com" />
</form>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-html5-17-01.jpeg)

<br>

- The `autofocus` attribute makes the desired input focus when the form loads:
  - `autofocus` 속성은 form이 로딩될 때 원하는 input focus를 만든다.

```html
<form>
   <label for="e-mail">Your e-mail address: </label>
   <input type="text" name="email" autofocus />
</form>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-html5-17-02.jpeg)

------

<br>

## Forms with Required Fields

###### 필수 입력란이 있는 form

<br>

- The `"required"` attribute is used to make the input elements required.
  - 필수 input element를 작성하는 데 `"required"` 속성이 사용된다.

```html
<form autocomplete="off">
   <label for="e-mail">Your e-mail address: </label>
   <input name="Email" type="text" required />
   <input type="submit" value="Submit" />
</form>
```

<br>

- The form will not be submitted without filling in the required fields.
  - 필수 입력란을 채우지 않고는 form이 제출되지 않는다.

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-html5-17-03.jpeg)

<br>

> The `autocomplete` attribute specifies whether a form or input field should have autocomplete turned on or off.
>
> `autocomplete` 속성은 form 또는 input field에서 자동완성 기능을 켜거나 끌지 여부를 지정한다.

> When autocomplete is on, the browser automatically complete values based on values that the user has entered before.
>
> 자동완성 기능이 켜지면, 브라우저는 사용자가 이전에 입력한 값에 따라 값을 자동으로 완성한다.

<br>

#### HTML5 added several new input types:

###### HTML5가 추가한 몇 가지 새로운 input types

- color
- date
- datetime
- datetime-local
- email
- month
- number
- range
- search
- tel
- time
- url
- week

<br>

#### New input attributes in HTML5:

###### HTML5의 새로운 input 속성

- autofocus
- form
- formaction
- formenctype
- formmethod
- formnovalidate
- formtarget
- height and width
- list
- min and max
- multiple
- pattern (regexp)
- placeholder
- required
- step

<br>

> Input types that are not supported by old web browsers, will behave as input type text.
>
> 이전 웹 브라우저에서 지원하지 않는 input type은 input type text로 작동한다.

------

<br>

## QUIZ

- Fill in the blanks:

```html
<form>
   <input type="text" name="name" />
</form>
```

<br>

- Drag and drop from the options below to auto focus on the input and create a placeholder.
  - 아래 옵션에서 드래그 앤 드랍해서 input에 auto focus를 지정하고 placeholder를 생성해라.

```html
<form>
   <input type="text" name="name" placeholder="Enter your name" autofocus />
</form>
```



<br>

- Designate the username field as required, and focus on the name field when the page loads:
  - 필요에 따라 username field를 지정하고, 페이지가 로딩될 때 name field에 초점을 맞춰라.

```html
<form autocomplete="off">
   <input name="name" type="text" autofocus />
   <br />
   <input name="username" type="text" required />
</form>
```

<br>
