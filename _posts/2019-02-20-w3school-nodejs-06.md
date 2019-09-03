---
layout: post
title: "(Node.js 06) File System 모듈"
categories: dev
tags: nodejs
---

###### [w3schools Node.js](https://www.w3schools.com/nodejs/) 번역

<br>

## Node.js as a File Server

###### 파일 서버로의 Node.js

- The Node.js file system module allows you to work with the file system on your computer.
  - Node.js File System 모듈을 사용하면, File System으로 작업할 수 있다.
- To include the File System module, use the `require()` method:
  - File System 모듈을 포함시키기 위해, `require()` 메소드를 사용한다.

```js
var fs = require('fs');
```

<br>

- Common use for the File System module:
  - File System 모듈의 일반적인 사용:
    - Create files (파일 생성하기)
    - Read files (파일 읽기)
    - Update files (파일 업데이트하기)
    - Delete files (파일 제거하기)
    - Rename files (파일 이름 변경하기)

<br>

<br>

### Create Files

###### 파일 생성하기

- The File System module has methods for creating new files:
  - File System 모듈에는 새 파일을 생성하는 메소드가 있다.
    - `fs.appendFile()`
    - `fs.open()`
    - `fs.writeFile()`

<br>

- The `fs.appendFile()` method appends specified content to a file.
  - `fs.appendFile()` 메소드는 지정된 내용을 파일에 추가한다.
- If the file does not exist, the file will be created:
  - 파일이 존재하지 않으면, 파일이 생성된다.

```js
var fs = require('fs');

fs.appendFile('mynewfile1.txt', 'Hello Content', function(err) {
  if (err) throw err;
  console.log('Saved!')
});
```

[코드 실행 확인](https://www.w3schools.com/nodejs/shownodejs_cmd.asp?filename=demo_fs_append)

<br>

- The `fs.open()` method takes a "flag" as the second argument, if the flag is "w" for "writing", the specified file is opened for writing.
  - `fs.open()` 메소드는 두 번째 인수로 "flag"를 사용한다.
  - flag가 "writing"에 대해 "w"라면, 지정된 파일을 작성하기 위해 열린다.
- If the file does not exist, an empty file is created:
  - 파일이 존재하지 않으면, 빈 파일이 생성된다.

```js
var fs = require('fs');

fs.open('mynewfile2.txt', 'w', function(err, file) {
  if (err) throw err;
  console.log('Saved!');
});
```

[코드 실행 확인](https://www.w3schools.com/nodejs/shownodejs_cmd.asp?filename=demo_fs_open)

<br>

- The `fs.writeFile()` method replaces the specified file and content if it exists.
  - `fs.writeFile()` 메소드는 지정된 파일과 내용을 대체한다.
- If the file does not exist, a new file, containing the specified content, will be created:
  - 파일이 존재하지 않으면, 지정된 내용을 포함하는 새 파일이 생성된다.

```js
var fs = require('fs');

fs.writeFile('mynewfile3.txt', 'Hello Content', function(err) {
  if (err) throw err;
  console.log('Saved!');
});
```

[코드 실행 확인](https://www.w3schools.com/nodejs/shownodejs_cmd.asp?filename=demo_fs_writefile)

<br>

<br>

### Read Files

###### 파일 읽기

- The `fs.readFile()` method is used to read files on your computer.
  - `fs.readFile()` 메소드는 파일을 읽는 데 사용된다.
- Assume we have the following HTML file (located in the same folder as Node.js).
  - 다음 HTML 코드를 "demofile1.html"에 저장한다.
  - (Node.js와 동일한 폴더에 저장)

```html
<html>
  <body>
    <h1>My Header</h1>
    <p>My paragraph.</p>
  </body>
</html>
```

<br>

- Create a Node.js file that reads the HTML file, and return the content:
  - HTML 파일을 읽는 Node.js 파일을 생성하고, 내용을 반환한다.

```js
var http = require('http');
var fs = require('fs');

http.createServer(function(req, res) {
  fs.readFile('demofile1.html', function(err, data) {
    res.writeHead(200, { 'Content-Type': 'text/html' });
    res.write(data);
    res.end();
  });
}).listen(8080);
```

[코드 실행 확인](https://www.w3schools.com/nodejs/shownodejs.asp?filename=demo_readfile)

<br>

- Save the code above in a file called "demo_readfile.js", and initiate the file:
  - 위 코드를 "demo_readfile.js" 파일에 저장하고 실행한다.

```bash
$ node demo_readfile.js
```

<br>

<br>

### Update Files

###### 파일 업데이트하기

- The File System module has methods for updating files:
  - File System 모듈에는 파일을 업데이트하는 메소드가 있다.
    - `fs.appendFile()`
    - `fs.writeFile()`

<br>

- The `fs.appendFile()` method appends the specified content at the end of the specified file:
  - `fs.appendFile()` 메소드는 지정된 파일의 끝에 지정된 내용을 추가한다.

```js
var fs = require('fs');

fs.appendFile('mynewfile1.txt', ' This is my text.', function(err) {
  if (err) throw err;
  console.log('Updated!');
});
```

[코드 실행 확인](https://www.w3schools.com/nodejs/shownodejs_cmd.asp?filename=demo_fs_update)

<br>

- The `fs.writeFile()` method replaces the specified file and content:
  - `fs.writeFile()` 메소드는 지정된 파일과 내용을 대체한다.

```js
var fs = require('fs');

fs.writeFile('mynewfile3.txt', 'This is my text', function(err) {
  if (err) throw err;
  console.log('Replaced!');
});
```

[코드 실행 확인](https://www.w3schools.com/nodejs/shownodejs_cmd.asp?filename=demo_fs_replace)

<br>

<br>

### Delete Files

###### 파일 제거하기

- To delete a file with the File System module, use the `fs.unlink()` method.
  - File System 모듈로 파일을 제거하기 위해, `fs.unlink()` 메소드를 사용한다.
- The `fs.unlink()` method deletes the specified file:
  - `fs.unlink()` 메소드는 지정된 파일을 제거한다.

```js
var fs = require('fs');

fs.unlink('mynewfile2.txt', function(err) {
  if (err) throw err;
  console.log('File deleted!');
});
```

[코드 실행 확인](https://www.w3schools.com/nodejs/shownodejs_cmd.asp?filename=demo_fs_unlink)

<br>

<br>

### Rename Files

###### 파일 이름 변경하기

- To rename a file with the File System module, use the `fs.rename()` method.
  - File System 모듈로 파일 이름을 변경하기 위해, `fs.rename()` 메소드를 사용한다.
- The `fs.rename()` method renames the specified file:
  - `fs.rename()` 메소드는 지정된 파일의 이름을 변경한다.

```js
var fs = require('fs');

fs.rename('mynewfile1.txt', 'myrenamedfile.txt', function(err) {
  if (err) throw err;
  console.log('File Renamed!');
});
```

[코드 실행 확인](https://www.w3schools.com/nodejs/shownodejs_cmd.asp?filename=demo_fs_rename)

<br>

<br>

### Upload Files

###### 파일 업로드하기

- You can also use Node.js to upload files to your computer.
  - Node.js를 사용해서 파일을 컴퓨터에 업로드할 수도 있다.

<br>

<br>