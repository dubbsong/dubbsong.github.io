---
layout: post
title: "(Node.js 09) 이벤트"
categories: dev
tags: nodejs
---

###### [w3schools Node.js](https://www.w3schools.com/nodejs/) 번역

<br>

## Events in Node.js

###### Node.js의 이벤트

- Every action on a computer is an event.
  - 컴퓨터의 모든 동작은 이벤트이다.
- Like when a connection is made or a file is opened.
  - 연결 또는 파일을 여는 것과 비슷하다.
- Objects in Node.js can fire events, like the readStream object fires events when opening and closing a file:
  - 파일을 열고 닫을 때 readStream 객체가 이벤트를 발생시키는 것처럼, Node.js의 객체도 이벤트를 발생시킬 수 있다.

```js
var fs = require('fs');
var rs = fs.createReadStream('./demofile.txt');

rs.on('open', function() {
  console.log('The file is open');
});
```

[코드 실행 확인](https://www.w3schools.com/nodejs/shownodejs_cmd.asp?filename=demo_events_open)

<br>

<br>

## Events Module

###### 이벤트 모듈

- Node.js has a built-in module, called "Events", where you can create\-, fire\-, and listen for\- your own events.
  - Node.js에는 "Events"라는 내장 모듈이 있다.
  - 자기 자신의 이벤트를 create\-, fire\-, listen for\- 할 수 있다.
- To include the built-in Events module use the `require()` method.
  - 내장 Events 모듈을 포함시키기 위해, `require()` 메소드를 사용한다.
- In addition, all event properties and methods are an instance of an EventEmitter object.
  - 모든 이벤트 속성 및 메소드는 EventEmitter 객체의 인스턴스이다.
- To be able to access these properties and methods, create an EventEmitter object:
  - 이러한 속성 및 메소드에 액세스하려면, EventEmitter 객체를 생성한다.

```js
var events = require('events');
var eventEmitter = new events.EventEmitter();
```

<br>

<br>

## The EventEmitter Object

###### EventEmitter 객체

- you can assign event handlers to your own events with the EventEmitter object.
  - EventEmitter 객체를 사용해서, 이벤트 핸들러를 자기 자신의 이벤트에 할당할 수 있다.
- In the example below we have created a function that will be executed when a "scream" event is fired.
  - 아래 예제에서, "scream" 이벤트가 발생할 때 실행될 함수를 생성했다.
- To fire an event, use the `emit()` method.
  - 이벤트를 발생시키기 위해, `emit()` 메소드를 사용한다.

```js
var events = require('events');
var eventEmitter = new events.EventEmitter();

// 이벤트 핸들러 생성
var myEventHandler = function() {
  console.log('I hear a scream!');
}

// 이벤트를 이벤트 핸들러에 할당
eventEmitter.on('scream', myEventHandler);

// 'scream' 이벤트 발생
eventEmitter.emit('scream');
```

[코드 실행 확인](https://www.w3schools.com/nodejs/shownodejs_cmd.asp?filename=demo_eventemitter)

<br>

<br>