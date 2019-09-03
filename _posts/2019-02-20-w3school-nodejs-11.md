---
layout: post
title: "(Node.js 11) 이메일 보내기"
categories: dev
tags: nodejs
---

###### [w3schools Node.js](https://www.w3schools.com/nodejs/) 번역

<br>

## The Nodemailer Module

###### Nodemailer 모듈

- The Nodemailer module makes it easy to send emails from your computer.
  - Nodemailer 모듈을 사용하면, 컴퓨터에서 이메일을 쉽게 보낼 수 있다.
- The Nodemailer module can be downloaded and installed using npm:
  - npm을 사용해서 Nodemailer 모듈을 다운로드하고 설치할 수 있다.

```bash
$ npm install nodemailer
```

<br>

- After you have downloaded the Nodemailer module, you can include the module in any application:
  - Nodemailer 모듈을 다운로드한 후, 모든 애플리케이션에서 모듈을 포함시킬 수 있다.

```js
var nodemailer = require('nodemailer');
```

<br>

<br>

## Send an Email

###### 이메일 보내기

- Now you are ready to send emails from your server.
  - 이제 서버에서 이메일을 보낼 준비가 되었다.
- Use the username and password from your selected email provider to send an email.
  - 선택한 이메일 제공자로부터 username과 password를 사용해서 이메일을 보낸다.
- This tutorial will show you how to use your Gmail account to send an email:
  - 아래 튜토리얼은 Gmail 계정을 사용해서 이메일을 보내는 방법을 보여준다.

```js
var nodemailer = require('nodemailer');

var transporter = nodemailer.createTransport({
  service: 'gmail',
  auth: {
    user: 'yourmail@gmail.com',
    pass: 'yourpassword'
  }
});

var mailOptions = {
  from: 'youremail@gmail.com',
  to: 'myfriend@naver.com',
  subject: 'Sending Email using Node.js',
  text: 'That was easy!'
};

transporter.sendMail(mailOptions, function(error, info) {
  if (error) {
    console.log(error);
  } else {
    console.log('Email sent: ' + info.response);
  }
});
```

<br>

- Now your server is able to send emails.
  - 이제 서버가 이메일을 보낼 수 있다.

<br>

<br>

## Multiple Receivers

###### 여러 수신기

- To send an email to more than one receiver, add them to the "to" property of the mailOptions object, sparated by commas:
  - 둘 이상의 수신자에게 이메일을 보내기 위해, mailOptions 객체의 "to" 속성에 쉼표로 구분해서 추가한다.

```js
var mailOptions = {
  from: 'youremail@gmail.com',
  to: 'myfriend@naver.com, myotherfriend@naver.com',
  subject: 'Sending Email using Node.js',
  text: 'That was easy!'
}
```

<br>

<br>

## Send HTML

###### HTML 보내기

- To send HTML formatted text in your email, use the "html" property instead of the "text" property:
  - 이메일에서 HTML 형식의 텍스트를 보내기 위해, "text" 속성 대신 "html" 속성을 사용한다.

```js
var mailOptions = {
  from: 'youremail@gmail.com',
  to: 'myfriend@naver.com',
  subject: 'Sending Email using Node.js',
  html: '<h1>Welcome</h1><p>That was easy!</p>'
}
```

<br>

<br>