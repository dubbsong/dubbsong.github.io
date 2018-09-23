---
layout: post
title: "(HTML5 17) form"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# HTML5 Forms

###### form

<br>

- HTML5 brings many features and improvements to web form creation.
  - HTML5는 웹 form 생성에 많은 향상된 기능을 제공한다.
- There are new attributes and input types that were introduced to help create better experiences for web users.
  - 웹 사용자에게 더 나은 경험을 제공하기 위해 도입된 새로운 속성과 input type이 있다.

<br>

- Form creation is done in HTML5 the same way as it was in HTML4:
  - form 생성은 HTML5에서 HTML4와 동일한 방식으로 수행된다.

```html
<form>
   <label>Your name: </label>
   <input id="user" name="username" type="text" />
</form>
```

[코드 실행 확인](https://code.sololearn.com/64/#html)

<br>

> Use the novalidate attribute to avoid form validation on submissions.
>
> 제출 시에 form 유효성 검사를 피하려면, novalidate 속성을 사용해라.

------

<br>

## New Attributes

###### 새로운 속성들

<br>

- HTML5 has introduced a new attribute called `placeholder`.
  - HTML5는 `placeholder`라는 새로운 속성을 도입했다.
- On `<input>` and `<textarea>` elements, this attribute provides a hint to the user of what information can be entered into the field.
  - `<input>`과 `<textarea>` element에서 이 속성은, field에 입력할 수 있는 정보의 힌트를 사용자에게 제공한다.

```html
<form>
   <label for="email">Your e-mail address: </label>
   <input type="text" name="email" placeholder="email@example.com" />
</form>
```

[코드 실행 확인](https://code.sololearn.com/65/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-html5-17-01.jpeg)

<br>

- The `autofocus` attribute makes the desired input focus when the form loads:
  - `autofocus` 속성은 form이 로딩될 때 원하는 input focus를 만든다.

```html
<form>
   <label for="e-mail">Your e-mail address: </label>
   <input type="text" name="email" autofocus />
</form>
```

[코드 실행 확인](https://code.sololearn.com/66/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-html5-17-02.jpeg)

<br>

> The required attribute tells the browser that the input is required.
>
> 필수 속성은 input이 필요하다는 것을 브라우저에게 알려준다.

------

<br>

## Forms with Required Fields

###### 필수 field가 있는 form

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

[코드 실행 확인](https://code.sololearn.com/67/#html)

<br>

- The form will not be submitted without filling in the required fields.
  - form은 필수 field를 채우지 않고는 제출되지 않는다.

<br>

- Result:

![img](/assets/img/html-sololearn-html5-17-03.jpeg)

<br>

> The `autocomplete` attribute specifies whether a form or input field should have autocomplete turned on or off.
>
> `autocomplete` 속성은 form 또는 input field에서 자동완성을 켜거나 끌지 여부를 지정한다.

> When autocomplete is on, the browser automatically complete values based on values that the user has entered before.
>
> 자동완성이 켜지면, 브라우저는 사용자가 이전에 입력한 값에 따라 값을 자동으로 완성한다.

<br>

- HTML5 added several new input types:
  - HTML5는 몇 가지 새로운 input type을 추가했다.
  - `color`, `date`, `datetime`, `datetime-local`, `email`, `month`, `number`, `range`, `search`, `tel`, `time`, `url`, `week`

<br>

- New input attributes in HTML5:
  - HTML5의 새로운 input 속성:
  - `autofocus`, `form`, `formaction`, `formenctype`, `formmethod`, `formnovalidate`, `formtarget`, `height and width`, `list`, `min and max`, `multiple`, `pattern (regexp)`, `placeholder`, `required`, `step`

<br>

> Input types that are not supported by old web browsers, will behave as input type text.
>
> 이전 웹 브라우저에서 지원하지 않는 input type은 input type text로 동작한다.

------

<br>

## Creating a Search Box

###### 검색창 생성

<br>

- The new `search` input type can be used to create a search box:
  - 새로운 `search` input type을 사용해서 검색창을 생성할 수 있다.

```html
<input id="mysearch" name="searchitem" type="search" />
```

[코드 실행 확인](https://code.sololearn.com/68/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-html5-17-04.png)

<br>

> You must remember to set a name for your input; otherwise, nothing will be submitted.
>
> input의 name을 반드시 설정해야 한다.
>
> 그렇지 않으면 아무것도 제출되지 않는다.

------

<br>

## Search Options

###### 검색 옵션

<br>

- The `<datalist>` tag can be used to define a list of pre-defined options for the search field:
  - `<datalist>` 태그는 search field에 대해 사전 정의된 옵션 list를 정의하는 데 사용할 수 있다.

```html
<input id="car" type="text" list="colors" />
<datalist id="colors">
   <option value="Red">
   <option value="Green">
   <option value="Yellow">
</datalist>
```

[코드 실행 확인](https://code.sololearn.com/69/#html)

<br>

- Result:

![img](/assets/img/html-sololearn-html5-17-05.jpeg)

<br>

- `<option>` defines the options in a drop-down list for the user to select.
  - `<option>`은 사용자가 선택할 수 있는 drop-down list의 옵션을 정의한다.

<br>

> The ID of the datalist element must match with the list attribute of the input box.
>
> datalist element의 ID는 input 상자의 list 속성과 일치해야 한다.

------

<br>

## Creating More Fields

###### 추가 field 생성

<br>

- Some other new input types include `email`, `url`, and `tel`:
  - 다른 새로운 input type에는 `email`, `url`, `tel`이 있다.

```html
<input id="email" name="email" type="email" placeholder="example@example.com" />
<br />
<input id="url" name="url" type="url" placeholder="example.com" />
<br />
<input id="tel" name="tel" type="tel" placeholder="555.555.1211" />
```

[코드 실행 확인](https://code.sololearn.com/70/#html)

<br>

- These are especially useful when opening a page on a modern mobile device, which recognizes the input types and opens a corresponding keyboard matching the field's type:
  - 이 기능은 최신 모바일 장치에서 페이지를 열 때 특히 유용하다.
  - input type을 인식하고, field type과 일치하는 키보드를 오픈한다.

![img](/assets/img/html-sololearn-html5-17-06.png)

<br>

> These new types make it easier to structure and validate HTML forms.
>
> 이러한 새로운 type을 사용하면 HTML form을 쉽게 구조화하고, 쉽게 유효성 검사를 할 수 있다.

------

<br>

## QUIZ

- Drag and drop from the options below to auto focus on the input and create a placeholder:
  - input에 auto focus하고, placeholder를 생성해라.

```html
<form>
   <input type="text" name="name"
          placeholder="Enter Your name" autofocus />
</form>
```

<br>

- Designate the username field as required, and focus on the name field when the page loads:
  - username field를 required로 지정하고, 페이지가 로딩될 때 name field에 focus 해라.

```html
<form autocomplete="off">
   <input name="name" type="text" autofocus />
   <br />
   <input name="username" type="text" required />
</form>
```

<br>

- Fill in the blanks to associate the input with the datalist:
  - input을 datalist에 연결해라.

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
  - 다음 중 input 태그에 지원되는 type이 아닌 것은 무엇인가?

> [ ] tel
>
> [ ] url
>
> [ ] `planet`
>
> [ ] submit

<br>