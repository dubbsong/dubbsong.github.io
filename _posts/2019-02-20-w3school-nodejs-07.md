---
layout: post
title: "(Node.js 07) url 모듈"
categories: dev
tags: nodejs
---

###### [w3schools Node.js](https://www.w3schools.com/nodejs/) 번역

<br>

## The Built-in URL Module

###### 내장 URL 모듈

- The URL module splits up a web address into readable parts.
  - URL 모듈은 웹 주소를 읽을 수 있는 부분으로 분할한다.
- To include the URL module, use the `require()` method:
  - URL 모듈을 포함시키기 위해, `require()` 메소드를 사용한다.

```js
var url = require('url');
```

<br>

- Parse an address with the `url.parse()` method, and it will return a URL object with each part of the address as properties.
  - `url.parse()` 메소드를 사용해서 주소를 구문 분석(parse)하면, 주소의 각 부분이 속성으로 된 URL 객체를 반환한다.

```js
var url = require('url');
var adr = 'http://localhost:8080/default.htm?year=2019&month=August';
var q = url.parse(adr, true);

console.log(q.host);       // localhost:8080
console.log(q.pathname);   // /default.htm
console.log(q.search);     // ?year=2019&month=August

var qdata = q.query;       // { year: 2019, month: 'August' }
console.log(qdata.month);  // August
```

[코드 실행 확인](https://www.w3schools.com/nodejs/shownodejs_cmd.asp?filename=demo_url)

<br>

<br>

## Node.js File Server

###### Node.js 파일 서버

- Now we know how to parse the query string, and in the previous chapter we learned how to make Node.js behave as a file server.
  - 이제 query 문자열을 구문 분석(parse)하는 방법을 알고 있다.
  - 그리고 이전 챕터에서 Node.js를 파일 서버로 작동시키는 방법을 배웠다.
- Let us combine the two, and serve the file requested by the client.
  - 이 두 가지를 결합하고, 클라이언트가 요청한 파일을 제공하겠다.

- Create two html files and save them in the same folder as your node.js files.
  - 두 개의 html 파일을 생성하고, node.js 파일과 동일한 폴더에 저장한다.

<br>

- summer.html

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>Summer</h1>
    <p>I love the sun!</p>
  </body>
</html>
```

<br>

- winter.html

```html
<!DOCTYPE html>
<html>
  <body>
    <h1>Winter</h1>
    <p>I love the snow!</p>
  </body>
</html>
```

<br>

- Create a Node.js file that opens the requested file and returns the content to the client.
  - 요청된 파일을 열고, 내용을 클라이언트로 반환하는 Node.js 파일을 생성한다.
- If anything goes wrong, throw a 404 error:
  - 문제가 발생하면, 404 에러를 반환한다.

<br>

- demo_fileserver.js

```js
var http = require('http');
var url = require('url');
var fs = require('fs');

http.createServer(function(req, res) {
  var q = url.parse(req.url, true);
  var filename = '.' + q.pathname;
  fs.readFile(filename, function(err, data) {
    if (err) {
      res.writeHead(404, { 'Content-Type': 'text/html' });
      return res.end('404 Not Found');
    }
    res.writeHead(200, { 'Content-Type': 'text/html' });
    res.write(data);
    return res.end();
  });
}).listen(8080);
```

<br>

- Remember to initiate the file:
  - 파일을 실행한다.

```bash
$ node demo_fileserver.js
```

> localhost:8080/summer.html: `Summer I love the sun!`
>
> localhost:8080/winter.html: `Winter I love the snow!`

<br>

- If you have followed the same steps on your computer, you should see two different results when opening these two addresses:
  - 이 두 주소를 열 때, 두 가지 다른 결과를 볼 수 있다.

<br>

<br>