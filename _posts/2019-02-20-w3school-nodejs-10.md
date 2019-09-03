---
layout: post
title: "(Node.js 10) 파일 업로드"
categories: dev
tags: nodejs
---

###### [w3schools Node.js](https://www.w3schools.com/nodejs/) 번역

<br>

## The Formidable Module

###### Formidable 모듈

- There is a very good module for working with file uploads, called "Formidable".
  - 파일 업로드 작업을 위한 "Formidable"이라는 아주 좋은 모듈이 있다.
- The Formidable module can be downloaded and installed using NPM:
  - NPM을 사용해서 Formidable 모듈을 다운로드하고 설치할 수 있다.

```bash
$ npm install formidable
```

<br>

- After you have downloaded the Formidable module, you can include the module in any application:
  - Formidable 모듈을 다운로드한 후, 모든 애플리케이션에 모듈을 포함시킬 수 있다.

```js
var formidable = require('formidable');
```

<br>

<br>

## Upload Files

###### 파일 업로드하기

- Now you are ready to make a web page in Node.js that lets the user upload files to your computer:
  - 이제 사용자가 컴퓨터에 파일을 업로드할 수 있는 웹 페이지를 만들 준비가 되었다.

<br>

### Step 1: Create an Upload Form

###### 1단계: 업로드 form 생성하기

- Create a Node.js file that writes an HTML form, with an upload field:
  - 업로드 필드를 사용해서, HTML form을 작성하는 Node.js 파일을 생성한다.

```js
var http = require('http');

http.createServer(function(req, res) {
  res.writeHead(200, { 'Content-Type': 'text/html' });
  res.write('<form action="fileupload" method="post" enctype="multipart/form-data">');
  res.write('<input type="file" name="filetoupload"><br>');
  res.write('<input type="submit">');
  res.write('</form>');
  return res.end();
}).listen(8080);
```

<br>

### Step 2: Parse the Uploaded File

###### 2단계: 업로드된 파일 구문 분석(parse) 하기

- Include the Formidable module to be able to parse the uploaded file once it reaches the server.
  - 업로드된 파일이 서버에 도달하면 구문 분석(parse) 할 수 있도록 Formidable 모듈을 포함시킨다.
- When the file is uploaded and parsed, it gets placed on a temporary folder on your computer.
  - 파일을 업로드하고 구문 분석(parse)하면, 컴퓨터의 임시 폴더에 저장된다.

```js
var http = require('http');
var formidable = require('formidable');

http.createServer(function(req, res) {
  if (req.url == '/fileupload') {
    var form = new formidable.IncomingForm();
    form.parse(req, function(err, fields, files) {
      res.write('File uploaded');
      res.end();
    });
  } else {
    res.writeHead(200, { 'Content-Type': 'text/html' });
    res.write('<form action="fileupload" method="post" enctype="multipart/form-data">');
    res.write('<input type="file" name="filetoupload"><br>');
    res.write('<input type="submit">');
    res.write('</form>');
    return res.end();
  }
}).listen(8080);
```

<br>

### Step 3: Save the File

###### 3단계: 파일 저장하기

- When a file is successfully uploaded to the server, it is placed on a temporary folder.
  - 파일이 서버에 성공적으로 업로드되면, 임시 폴더에 저장된다.
- The path to this directory can be found in the "files" object, passed as the third argument in the `parse()` method's callback function.
  - 이 디렉토리의 경로는 "files" 객체에서 찾을 수 있다.
  - `parse()` 메소드의 콜백 함수에서 세 번째 인수로 전달된다.
- To move the file to the folder of your choice, use the File System module, and rename the file:
  - 파일을 선택한 폴더로 이동시키기 위해, 파일 시스템 모듈을 사용하고, 파일 이름을 변경한다.

```js
var http = require('http');
var formidable = require('formidable');
var fs = require('fs');

http.createServer(function(req, res) {
  if (req.url == '/fileupload') {
    var form = new formidable.IncomingForm();
    form.parse(req, function(err, fields, files) {
      var oldpath = files.filetoupload.path;
      var newpath = 'C:/Users/Your Name/' + files.filetoupload.name;
      fs.rename(oldpath, newpath, function(err) {
        if (err) throw err;
        res.write('File uploaded and moved!');
        res.end();
      });
    });
  } else {
    res.writeHead(200, { 'Content-Type': 'text/html' });
    res.write('<form action="fileupload" method="post" enctype="multipart/form-data">');
    res.write('<input type="file" name="filetoupload"><br>');
    res.write('<input type="submit">');
    res.write('</form>');
    return res.end();
  }
}).listen(8080);
```

<br>

<br>