---
layout: post
title: "(Node.js 03) 시작하기"
categories: dev
tags: nodejs
---

###### [w3schools Node.js](https://www.w3schools.com/nodejs/) 번역

<br>

## Download Node.js

###### Node.js 다운로드

- The official Node.js website has installation instructions for Node.js: https://nodejs.org
  - [공식 Node.js 웹사이트](https://nodejs.org)에는 Node.js에 대한 설치 지침이 있다.

<br>

<br>

## Getting Started

###### 시작하기

- Once you have download and installed Node.js on your computer, let's try to display "Hello World" in a web browser.
  - 웹 브라우저에 "Hello World"를 표시해보자.
- Create a Node.js file named "myfirst.js", and add the following code:
  - "myfirst.js"라는 Node.js 파일을 생성하고, 다음 코드를 추가한다.

<br>

- myfirst.js

```js
var http = require('http');

http.createServer(function(req, res) {
  res.writeHead(200, { 'Content-Type': 'text/html' });
  res.end('Hello World');
}).listen(8080);
```

<br>

- Save the file on your computer: `C:\Users/Your Name\myfirst.js`
  - `C:\Users/Your Name\myfirst.js`에 파일을 저장한다.
- The code  tells the computer to write "Hello World" if anyone (e.g. a web browser) tries to access your computer on port 8080.
  - 웹 브라우저가 port 8080에 액세스하는 경우, 위 코드는 컴퓨터에게 "Hello World"를 작성하라고 지시한다.
- For now, you do not have to understand the code. It will be explained later.
  - 지금은 코드를 이해할 필요가 없다. 나중에 설명할 것이다.

<br>

<br>

## Command Line Interface

###### 명령 줄 인터페이스 (CLI)

- Node.js files must be initiated in the "Command Line Interface" program of your computer.
  - Node.js 파일은 컴퓨터의 "CLI" 프로그램에서 실행되어야 한다.
- How to open the command line interface on your computer depends on the operating system.
  - 컴퓨터에서 CLI를 여는 방법은 운영 시스템에 따라 다르다.
- For Windows users, press the start button and look for "Command Prompt", or simply write "cmd" in the search field.
  - Windows 사용자의 경우, 시작 버튼을 누르고 "명령 프롬프트"를 찾거나, 검색 필드에 "cmd"를 작성한다.
- Navigate to the folder that contains the file "myfirst.js", the command line interface window should look something like this:
  - "myfirst.js" 파일이 포함된 폴더로 이동하면, CLI가 다음과 같아야 한다.

```bash
C:\Users\Your Name> _
```

<br>

<br>

## Initiate the Node.js File

###### Node.js 파일 실행하기

- The file you have just created must be initiated by Node.js before any action can take place.
  - 방금 생성한 파일은 Node.js에 의해 실행되어야 한다.
- Start your command line interface, write `node myfirst.js` and hit enter:
  - CLI를 열어 `node myfirst.js`를 작성한 후, Enter를 누른다.

<br>

- Windows Command Prompt

```bash
C:\Users\Your Name> node myfirst.js
```

- Mac OS Terminal

```bash
$ node myfirst.js
```

<br>

- Now, your computer works as a server.
  - 이제 컴퓨터가 서버로 작동한다.
- If anyone tries to access your computer on port 8080, they will get a "Hello World" message in return.
  - port 8080에 액세스하면 "Hello World" 메시지가 표시된다.
- Start your internet browser, and type in the address: http://localhost:8080
  - 인터넷 브라우저를 열어 http://localhost:8080을 입력한다.

<br>

<br>