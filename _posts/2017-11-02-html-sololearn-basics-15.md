---
layout: post
title: "(Basics 15) 블로그 프로젝트: Contact Form"
categories: html
---

###### [SoloLearn](https://www.sololearn.com/) HTML 번역

<br>

# Blog Project: Contact Form

###### 블로그 프로젝트: Contact Form

<br>

- Next, we'll create a `Contact Form` for your blog.
  - 다음으로, 블로그에 대한 `Contact Form`을 생성해보자.
- The form will include Name, Email, and Message fields.
  - form에는 Name, Email, Message field가 포함된다.
- We'll also add a Submit button.
  - Submit 버튼도 추가해보자.

```html
<h1><span>Contact Me</span></h1>
<form>
   <input name="name" type="text" /><br />
   <input name="name" type="email" /><br />
   <textarea name="message"></textarea>
   <input type="submit" value="SEND" class="submit" />
</form>
```

[코드 실행 확인](https://code.sololearn.com/1149/#html)

<br>

- This is just a static HTML page, so it won't work to actually submit the form.
  - 이것은 정적인 HTML 페이지일 뿐이므로, form을 실제로 제출하는 것은 효과가 없다.
- You'd need to create the server-side code in order to submit a real form and process the data.
  - 실제 form을 제출하고 데이터를 처리하려면, 서버 쪽 코드를 작성해야 한다.

------

<br>

## QUIZ

- To support multiple lines of input you should use the following element:
  - 여러 줄의 input을 지원하려면, 어떤 element를 사용해야 하는가?

> `textarea`

<br>