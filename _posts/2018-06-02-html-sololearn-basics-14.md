---
layout: post
title: "(Basics 14) Form"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML Form

------

<br>

<br>

## The \<form> Element

###### \<form> element

<br>

- HTML forms are used to collect information from the user.
  - HTML form은 사용자로부터 정보를 수집하는 데 사용된다.
- Forms are defined using the `<form>` element, with its opening and closing tags:
  - Form은 `<form>` element의 여는 태그와 닫는 태그를 사용해서 정의된다.

```html
<body>
   <form>...</form>
</body>
```

<br>

- Use the `action` attribute to print to a webpage that will load after the user submits the form.
  - `action` 속성을 사용해서 사용자가 form을 제출한 후에 로딩할 웹페이지를 출력한다.

```html
<form action="https://www.sololearn.com">
</form>
```

<br>

> Usually the form is submitted to a webpage on a web server
>
> 일반적으로 form은 웹 서버의 웹페이지에 제출된다.

------

<br>

## The method & name Attributes

###### method 속성 & name 속성

<br>

- The `method attribute` specifies the HTTP method (`GET` or `POST`) to be used when forms are submitted:
  - `method 속성`은 form을 제출할 때 사용할 HTTP 메소드(`GET` 또는 `POST`)를 지정한다.

```html
<form action="url" method="GET">
```

```html
<form action="url" method="POST">
```

<br>

> When you use `GET`, the form data will be visible in the page address.
>
> `GET`을 사용하면, form 데이터가 페이지 주소에 보여진다.

> Use `POST` if the form is updating data, or includes sensitive information (password).
>
> form에서 데이터를 업데이트하거나, 중요한 정보(비밀번호)가 포함되어 있으면, `POST`를 사용해라.
>
> POST offers better security because the submitted data is not visible in the page address.
>
> 제출된 데이터가 페이지 주소에 보여지지 않기 때문에, POST가 더 나은 보안을 제공한다.

<br>

- To take in user input, you need the corresponding form elements, such as text fields.
  - 사용자 input을 받으려면, 텍스트 field와 같은 해당 form element가 필요하다.
- The `<input>` element has many variations, depending on the type attribute.
  - `<input>` element는 type 속성에 따라 다양한 변화가 있다.
- It can be a text, password, radio, URL, submit, etc.
  - text, password, radio, URL, submit 등이 될 수 있다.

<br>

- The example below shows a form requesting a username and password:
  - 아래 예제는 username과 password를 요청하는 form을 보여준다.

```html
<form>
   <input type="text" name="username" /><br />
   <input type="password" name="password" />
</form>
```

[코드 실행 확인](https://code.sololearn.com/30/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-basics-14-01.jpeg)

<br>

> The name attribute specifies a name for a form.
>
> name 속성은 form의 이름을 지정한다.

------

<br>

## Form Elements

###### form element

<br>

- If we change the input type to `radio`, it allows the user select only one of a number of choices:
  - input type을 `radio`로 변경하면, 사용자가 여러 선택 사항 중 하나만 선택할 수 있다.

```html
<input type="radio" name="gender" value="male" />Male<br />
<input type="radio" name="gender" value="female" />Female<br />
```

[코드 실행 확인](https://code.sololearn.com/31/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-basics-14-02.jpeg)

<br>

- The type "checkbox" allows the user to select more than one option:
  - "checkbox" type을 사용하면, 사용자가 하나 이상의 옵션을 선택할 수 있다.

```html
<input type="checkbox" name="gender" value="1" />Male<br />
<input type="checkbox" name="gender" value="2" />Female<br />
```

[코드 실행 확인](https://code.sololearn.com/32/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-basics-14-03.jpeg)

<br>

> The \<input> tag has no end tag.
>
> \<input> 태그에는 종료 태그가 없다.

<br>

<br>

- The submit button `submits a form` to its action attribute:
  - submit 버튼은 action 속성에 `form을 제출`한다.

```html
<input type="submit" value="Submit" />
```

[코드 실행 확인](https://code.sololearn.com/33/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-basics-14-04.jpeg)

<br>

> After the form is submitted, the data should be processed on the server using a programming language, such as PHP.
>
> form을 제출한 후에는, PHP와 같은 프로그래밍 언어를 사용해 서버에서 데이터를 처리해야 한다.

------

<br>

## QUIZ

- Which attribute contains the URL address of the webpage that is loaded after a form submission?
  - form 제출 후에 로딩되는 웹페이지의 URL 주소를 포함하는 속성은 무엇인가?

> `action`

<br>

- Which value for the type attribute should be used for a password field?
  - password field에 어떤 type 속성을 사용해야 하는가?

> `<input type="password">`

<br>

- Which value for the type attribute turns the input tag into a submit button?
  - type 속성에 대한 어떤 값으로 input 태그를 submit 버튼으로 변환할 수 있나?

> `submit`

<br>