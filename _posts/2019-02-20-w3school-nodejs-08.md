---
layout: post
title: "(Node.js 08) npm"
categories: dev
tags: nodejs
---

###### [w3schools Node.js](https://www.w3schools.com/nodejs/) 번역

<br>

## What is NPM?

###### NPM은 무엇인가?

- NPM is a package manager for Node.js packages, or modules if you like.
  - NPM은 Node.js 패키지, 또는 원하는 module에 대한 패키지 관리자이다.
- www.npmjs.com hosts thousands of free packages to download and use.
  - www.npmjs.com에서 수천 개의 무료 패키지를 다운로드하고 사용할 수 있다.
- The NPM program is installed on your computer when you install Node.js.
  - Node.js를 설치할 때, 컴퓨터에 NPM 프로그램이 설치된다.

> NPM is already ready to run on your computer.
>
> NPM은 이미 컴퓨터에서 실행할 준비가 되어 있다.

<br>

<br>

## What is a Package?

###### 패키지는 무엇인가?

- A package in Node.js contains all the files you need for a module.
  - Node.js의 패키지에는 모듈에 필요한 모든 파일이 포함되어 있다.
- Modules are JavaScript libraries you can include in your project.
  - 모듈(Module)은 프로젝트에 포함할 수 있는 JS 라이브러리이다.

<br>

<br>

## Download a Package

###### 패키지 다운로드하기

- Downloading a package is very easy.
  - 패키지 다운로드는 아주 쉽다.
- Open the command line interface and tell NPM to download the package you want.
  - 원하는 패키지를 다운로드하기 위해, CLI를 열고 NPM에 지시한다.
- I want to download a package called "upper-case":
  - "upper-case"라는 패키지를 다운로드해보자.

```bash
$ npm install upper-case
```

<br>

- Now you have downloaded and installed your first package.
  - 이제 첫 번째 패키지를 다운로드하고 설치했다.
- NPM creates a folder named "node_modules", where the package will be placed.
  - NPM은 패키지가 위치할 곳에 "node_modules"라는 폴더를 생성한다.
- All packages you install in the future will be placed in this folder.
  - 나중에 설치하는 모든 패키지는 이 폴더에 설치된다.

<br>

<br>

## Using a Package

###### 패키지 사용하기

- Once the package is installed, it is ready to use.
  - 패키지가 설치되었다면 사용할 준비가 된 것이다.
- Include the "upper-case" package the same way you include any other module:
  - 다른 모듈을 포함하는 것과 같은 방법으로, "upper-case" 패키지를 포함시킨다.

```js
var uc = require('upper-case');
```

<br>

- Create a Node.js file that will convert the output "Hello World" into upper-case letters:
  - "Hello World"를 대문자로 변환할 Node.js 파일을 생성한다.

```js
var http = require('http');
var uc = require('upper-case');

http.createServer(function(req, res) {
  res.writeHead(200, { 'Content-Type': 'text/html' });
  res.write(uc("Hello World"));
  res.end();
}).listen(8080);
```

[코드 실행 확인](https://www.w3schools.com/nodejs/shownodejs.asp?filename=demo_uppercase)

<br>

- Save the code above in a file called "demo_uppercase.js", and initiate file:
  - 위 코드를 "demo_uppercase.js"라는 파일에 저장하고 실행한다.

```bash
$ node demo_uppercase.js
```

<br>

<br>

