---
layout: post
title: "SoloLearn HTML 번역 - 14. Forms (Basics)"
categories: dev
tags: html
---

###### [SoloLearn HTML 번역](www.sololearn.com)

<br>

## The \<form> Element

###### \<form> element

<br>

- HTML forms are used to collect information from the user.
  - HTML form은 사용자로부터 정보를 수집하는 데 사용된다.
- Forms are defined using the `<form>` element, with its opening and closing tags:
  - form은  `<form>` element의 여는 태그와 닫는 태그를 사용해서 정의된다.
  - `<form>`: Defines an HTML form for user input

```html
<body>
   <form>
      ...
   </form>
</body>
```

<br>

- Use the `action` attribute to point to a web page that will load after the user submits the form.
  - `action` 속성을 사용해서 사용자가 form을 제출한 후에 로드할 웹 페이지를 가리킨다.

```html
<form action="http://www.sololearn.com">
   
</form>
```

<br>

> Usually the form is submitted to a web page on a web server.
>
> 보통 form은 웹 서버의 웹 페이지에 제출된다.

------

<br>

## The method and name Attributes

###### method와 name 속성

<br>

- The `method attribute` specifies the HTTP method (`GET` or `POST`) to be used when forms are submitted:
  - `method 속성`은 form을 제출할 때 사용할 HTTP method(`GET` 또는 `POST`)를 지정한다.

```html
<form action="url" method="GET">
```

<br>

```html
<form action="url" method="POST">
```

<br>

> When you use `GET`, the form data will be visible in the page address.
>
> `GET`을 사용하면, form 데이터가 페이지 주소에 보이게 된다.

> Use `POST` if the form is updating data, or includes sensitive information (passwords).
>
> form이 데이터를 업데이트하거나, 중요한 정보(비밀번호)가 포함되어 있으면 `POST`를 사용해라.

> POST offers better security because the submitted data is not visible in the page address.
>
> 제출된 데이터가 페이지 주소에 보이지 않기 때문에 POST가 더 나은 보안을 제공한다.

<br>

- The `name attribute` specifies a name for a form.
  - `name 속성`은 form의 이름을 지정한다.

<br>

- To take in user input, you need the corresponding form elements, such as text fields.
  - 사용자 입력을 받기 위해서는, 텍스트 field와 같은 form element가 필요하다.
- The `<input>` element has many variations, depending on the type attribute.
  - `<input>` element는 type 속성에 따라 다양한 변형이 있다.
  - `<input>`: Defines an input control
- It can be a text, password, radio, URL, submit, etc.
  - type 속성은 텍스트, 비밀번호, 라디오, URL, 제출 등이 될 수 있다.

<br>

- The example below shows a form requesting a username and password:
  - 아래 예제는 사용자 이름과 비밀번호를 요청하는 form을 보여준다.

```html
<form>
   <input type="text" name="username"/><br />
   <input type="password" name="password" />
</form>
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-basics-14-01.jpeg)

------

<br>

## Form Elements

- If we change the input type to `radio`, it allows the user select only one of a number of choices:
  - input type을 `radio`로 변경하면, 사용자가 여러 선택 사항 중 하나만 선택할 수 있다.

```html
<input type="radio" name="gender" value="male" /> Male <br />
<input type="radio" name="gender" value="female" /> Female <br />
```

<br>

- Result:

![sololearn img](/aseets/img/sololearn-html-basics-14-02.jpeg)

<br>

- The type "checkbox" allows the user to select more than one option:
  - "checkbox" type은 사용자가 하나 이상의 옵션을 선택할 수 있게 한다.

```html
<input type="checkbox" name="gender" value="1" /> Male <br />
<input type="checkbox" name="gender" value="2" /> Female <br />
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-basics-14-03.jpeg)

------

<br>

## Form Elements 02

- The submit button `submits a form` to its action attribute:
  - submit 버튼은 action 속성에 `form을 제출`한다.

```html
<input type="submit" value="Submit" />
```

<br>

- Result:

![sololearn img](/assets/img/sololearn-html-basics-14-04.jpeg)

<br>

> After the form is submitted, the data should be processed on the server using a programming language, such as PHP.
>
> form을 제출한 후에는, PHP와 같은 프로그래밍 언어를 사용해 서버에서 데이터를 처리해야 한다.

------

<br>

## QUIZ

- Which attribute contains the URL address of the web page that is loaded after a form submission?
  - form 제출 후에 로드되는 웹 페이지의 URL 주소를 포함하는 속성은 무엇인가?

> [ ] method
>
> [ ] name
>
> [x] action
>
> [ ] id

<br>

- Which value for the type attribute should be used for a password field?
  - password field에는 type 속성의 어떤 값을 사용해야 하는가?

```html
<input type="password">
```

<br>

- Fill in the blanks:
  - 빈칸을 채워라.

```html
<form method="POST" action="#">
   <input type="text" name="name">
   <input type="submit" name="submit">
</form>
```

<br>

- Which value for the type attribute turns the input tag into a submit button?
  - type 속성에 대한 어떤 값으로 input 태그를 submit 버튼으로 바꿀 수 있는가?

> [x] submit
>
> [ ] radio
>
> [ ] checkbox
>
> [ ] button

<br>