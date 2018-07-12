---
layout: post
title: "SoloLearn HTML 번역 - 15. Blog Project: Contact Form (Basics)"
categories: dev
tags: html
---

## Contact Form

- Next, we'll create a `Contact Form` for your blog.
  - 다음으로, 블로그에 대한 `Contact Form`을 작성할 것이다.
- The form will include Name, Email, and Message fields.
  - form은 Name, Email, Message field를 포함한다.
- We'll also add a Submit button.
  - Submit 버튼도 추가할 것이다.
- Check out the code:
  - 코드를 살펴보자.

```html
<h1><span>Contact Me</span></h1>
<form>
   <input name="name" type="text" /><br/>
   <input name="email" type="email" /><br/>
   <textarea name="message"></textarea>
   <input type="submit" value="SEND" class="submit" />
</form>
```

<br>

- This is just a static HTML page, so it won't work to actually submit the form.
  - 이것은 정적인 HTML 페이지일 뿐이므로, form을 실제로 제출하는 것은 소용없다.
- You'd need to create the server-side code in order to submit a real form and process the data.
  - 실제 form을 제출하고 데이터를 처리하려면, 서버-사이드 코드를 작성해야 한다.
- To learn how, complete SoloLearn's PHP course once you've completed the HTML and CSS courses.
  - 배우는 방법은, HTML과 CSS 코드를 마치고 SoloLearn의 PHP course를 완료해라.

------

<br>

## QUIZ

- To support multiple lines of input you should use the following element:
  - 여러 줄의 입력을 지원하려면 다음 element를 사용해야 한다.

> [ ] text
>
> [ ] multipletext
>
> [x] `textarea`

<br>