---
layout: post
title: "(Node.js 04) 모듈"
---

###### [w3schools Node.js](https://www.w3schools.com/nodejs/) 번역

<br>

## What is a Module in Node.js?

###### Node.js에서 모듈(Module)은 무엇인가?

- Consider modules to be the same as JavaScript libraries.
  - 모듈(Module)을 JS 라이브러리로 생각해보자.
- A set of functions you want to include in your application.
  - 모듈은 애플리케이션에 포함시키려는 함수 집합이다.

<br>

<br>

## Built-in Modules

###### 내장 모듈

- Node.js has a set of built-in modules which you can use without any further installation.
  - Node.js에는 추가 설치 없이 사용할 수 있는 내장 모듈 집합이 있다.
- Look at our [Built-in Modules Reference](https://www.w3schools.com/nodejs/ref_modules.asp) for a complete list of modules.
  - 전체 모듈 리스트는 [Built-in Modules Reference](https://www.w3schools.com/nodejs/ref_modules.asp)를 참조한다.

<br>

<br>

## Include Modules

###### 모듈 포함하기

- To include a module, use the `require()` function with the name of the module:
  - 모듈을 포함하려면, `require()` 함수를 모듈의 이름과 함께 사용한다.

```js
var http = require('http');
```

<br>

- Now your application has access to the HTTP module, and is able to create a server:
  - 이제 애플리케이션이 HTTP 모듈에 액세스 할 수 있다.
  - 그리고 서버를 생성할 수 있다.

```js
http.createServer(function (req, res) {
  res.writeHead(200, { 'Content-Type': 'text/html' });
  res.end('Hello World');
}).listen(8080);
```

<br>

<br>

## Create Your Own Modules

###### 자기 자신만의 모듈 생성하기

- You can create your own modules, and easily include them in your applications.
  - 자기 자신만의 모듈을 생성해서, 애플리케이션에 쉽게 포함시킬 수 있다.
- The following example creates a module that returns a date and time object:
  - 다음 예제는 날짜 및 시간 객체를 반환하는 모듈을 생성한다.

```js
exports.myDateTime = function() {
  return Date();
};
```

<br>

- Use the `exports` keyword to make properties and methods available outside the module file.
  - 모듈 파일 외부에서 속성과 메소드를 사용하려면, `exports` 키워드를 사용한다.
- Save the code above in a file called "myfirstmodule.js".
  - 위 코드를 "myfirstmodule.js" 파일에 저장한다.

<br>

<br>

## Include Your Own Module

###### 자기 자신만의 모듈 포함하기

- Now you can include and use the module in any of your Node.js files.
  - 이제 Node.js 파일에 모듈을 포함시켜 사용할 수 있다.

```js
var http = require('http');
var dt = require('./myfirstmodule');

http.createServer(function (req, res) {
  res.writeHead(200, { 'Content-Type': 'text/html' });
  res.write('The date and time are currently: ' + dt.myDateTime());
  res.end();
}).listen(8080);
```

[코드 실행 확인](https://www.w3schools.com/nodejs/shownodejs.asp?filename=demo_module)

<br>

- Notice that we use `./` to locate the module, that means that the module is located in the same folder as the Node.js file.
  - `./`를 사용해서 모듈을 찾는다.
  - 즉, 모듈이 Node.js 파일과 동일한 폴더에 위치한다.
- Save the code above in a file called "demo_module.js", and initiate the file:
  - 위 코드를 "demo_module.js" 파일에 저장하고 실행한다.

```bash
$ node demo_module.js
```

<br>

<br>